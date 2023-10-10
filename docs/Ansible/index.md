# Ansible

_Disclaimer_: This is not an all inclusive guide but more of a good starting point.  I'd recommend you research and learn some on your own as much as you can.
Some of these are geared towards Windows, but I'll do my best to discern between the environments whenever possible.

## Install Ansible

_Disclaimer_: Because I'm stubborn, and primarily a Windows Systems Admin, much of this environment is performed from a Windows machine. That said, I _run_ Ansible scripts from a Linux subsystem in Windows.  See [getting Ubuntu for WSL](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#2-install-wsl) for more information.

### Deployment machine (Ansible Host)

First, get Ansible installed.

```
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```

These are needed for using Ansible to configure Windows hosts.

```
ansible-galaxy collection install ansible.windows
ansible-galaxy collection install chocolatey.chocolatey
apt-get install python3-pip
pip install pywinrm[credssp]
```

## On Target Windows Hosts

Windows needs a bit of setup before it's Ansible friendly.

```
# Collect some information and generate self-signed cert on host

$hostName = $env:COMPUTERNAME
$hostIP=(Get-NetAdapter| Get-NetIPAddress).IPv4Address|Out-String
$srvCert = New-SelfSignedCertificate -DnsName $hostName,$hostIP -CertStoreLocation Cert:\LocalMachine\My
$srvCert

# Clean up existing WinRM listeners and create new HTTPS WinRM listener with new cert

Get-ChildItem wsman:\localhost\Listener
Get-ChildItem wsman:\localhost\Listener\ | Where-Object -Property Keys -like 'Transport=HTTP*' | Remove-Item -Recurse
New-Item -Path WSMan:\localhost\Listener\ -Transport HTTPS -Address * -CertificateThumbPrint $srvCert.Thumbprint -Force

# Create new FW rules

New-NetFirewallRule -Displayname 'WinRM - Powershell remoting HTTPS-In' -Name 'WinRM - Powershell remoting HTTPS-In' -Profile Any -LocalPort 5986 -Protocol TCP

# Restart WinRM Service

Restart-Service WinRM

# Create and export certificates
New-Item -Path 'C:\Certificates\' -ItemType Directory
Export-Certificate -Cert $srvCert -FilePath C:\Certificates\SSL_PS_Remoting.cer
winrm set winrm/config/service '@{AllowUnencrypted="false"}'
winrm set winrm/config/client '@{AllowUnencrypted="false"}'

# Enable CredSSP
Enable-WSManCredSSP -Role Server -Force
```