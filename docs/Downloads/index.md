# Downloads

## Tools

### Chocolatey

Here are a list of tools that I use all the time. And typically ones that I get installed right away.

* [Chocolatey](https://chocolatey.org/install)
* [Official Chocolatey Install Guide](https://chocolatey.org/install)
* Install Chocolatey via PowerShell
    * First, you need to run this in an elevated PowerShell prompt (run as admin)
        * [Supported Windows client and server Operating Systems](https://docs.chocolatey.org/en-us/chocolatey-components-dependencies-and-support-lifecycle#supported-windows-versions) (can run on older Operating Systems)
        * PowerShell v2+ (minimum is v3 for install from this website due to [TLS 1.2 requirement](https://chocolatey.org/blog/remove-support-for-old-tls-versions))
        * .NET Framework 4.8 (the installation will attempt to install .NET 4.8 if you do not have it installed)

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Software

_Much of the software below can be installed via Chocolatey FYI!_

#### Notepad++

* [Notepad++](https://notepad-plus-plus.org/downloads/). With chocolatey:

```
choco install notepadplusplus
```

#### 7zip
* [7zip](https://www.7-zip.org/download.html). With chocolatey:

```
choco install 7zip
```

#### VSCode
* [VSCode](https://code.visualstudio.com/download). With chocolatey:

```
choco install vscode
```

#### Filezilla Client
* [Filezilla Client](https://filezilla-project.org/download.php). With chocolatey:

```
choco install filezilla
```

#### Putty
* [Putty](https://www.putty.org/). With chocolatey:

```
choco install putty
```

#### WinSCP
* [WinSCP](https://winscp.net/eng/download.php). With chocolatey:

```
choco install winscp
```

#### Git for Windows
* [Git for Windows](https://git-scm.com/download/win). With chocolatey:

```
choco install git
```

#### Bootable USB
* [Rufus](https://rufus.ie/en/) 

#### Windows Terminal
* [Windows Terminal](https://apps.microsoft.com/detail/windows-terminal/9N0DX20HK701?hl=en-us&gl=US)

## Operating Sytems

### Ubuntu
* [Ubuntu](https://ubuntu.com/download/server)

### CentOS
* [CentOS](https://www.centos.org/download/)

### Fedora
* [Fedora](https://fedoraproject.org/workstation/download/)

### Linux Mint
* [Mint](https://www.linuxmint.com/download.php)