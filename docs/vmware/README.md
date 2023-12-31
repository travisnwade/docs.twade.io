# VMware

## Start and Stop or Restart vCenter Server 6.x Services

For reference: [VMware 2109881](https://kb.vmware.com/s/article/2109881)

### List Services

Run this command to list the vCenter Server and/or Platform Services Controller services:

```
service-control --list
```

### Start a specific service

Start a specific service:

```
service-control --start servicename
```

### Start all services

Start all services:

```
service-control --start --all
```

### Stop a specific service

Stop a specific service:

```
service-control --stop servicename
```

### Stop all services

Stop all services:

```
service-control --stop --all
```

## Detailed description of VCSA Services

```
vmdnsd (VMware Domain Name Service)
vmware-vmon (VMware Service Lifecycle Manager)
vsan-dps (VMware VSAN Data Protection Service)
vmware-eam (VMware ESX Agent Manager)
vmafdd (VMware Authentication Framework)
vmware-sts-idmd (VMware Identity Management Service)
vsphere-ui (VMware vSphere Client)
applmgmt (VMware Appliance Management Service)
vmware-sca (VMware Service Control Agent)
vmware-vapi-endpoint (VMware vAPI Endpoint)
vmware-content-library (VMware Content Library Service)
vmware-vcha (VMware vCenter High Availability)
vmware-vsm (VMware vService Manager)
vmware-vsan-health (VMware VSAN Health Service)
vmware-vpxd (VMware vCenter Server)
vmware-mbcs (VMware Message Bus Configuration Service)
vmware-cm (VMware Component Manager)
vmware-pod (VMware Patching and Host Management Service)
vmdird (VMware Directory Service)
vmware-vpostgres (VMware Postgres)
lwsmd (Likewise Service Manager)
vmware-rhttpproxy (VMware HTTP Reverse Proxy)
vmware-statsmonitor (VMware Appliance Monitoring Service)
vmware-cis-license (VMware License Service)
vmware-analytics (VMware Analytics Service)
vmware-netdumper (VMware vSphere ESXi Dump Collector)
vmcam (VMware vSphere Authentication Proxy)
pschealth (VMware Platform Services Controller Health Monitor)
vmonapi (VMware Service Lifecycle Manager API)
vsphere-client (VMware vSphere Web Client)
vmware-rbd-watchdog (VMware vSphere Auto Deploy Waiter)
vmware-vpxd-svcs (VMware vCenter-Services)
vmware-postgres-archiver (VMware Postgres Archiver)
vmware-imagebuilder (VMware Image Builder Manager)
vmware-stsd (VMware Security Token Service)
vmcad (VMware Certificate Service)
vmware-perfcharts (VMware Performance Charts)
vmware-updatemgr (VMware Update Manager)
vmware-sps (VMware vSphere Profile-Driven Storage Service)
```