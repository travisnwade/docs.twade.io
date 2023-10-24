# Windows

## Monitor with WMI remotely without being a local administrator

This is something that I've fought with time and time again. I largely use [PRTG](https://www.paessler.com/) as a monitoring tool which is fantastic because it doesn't require remote agents to gather performance data.

The downside, is if you want to stay in line with security best practices, your service account that you utilize with PRTG you'd rather not make it a Domain Administrator just to simply give it the necessary permissions to read performance metrics.

Now, this may be overkill, but here's what I've manged to achieve in order to grant the active directory service account I use with PRTG so that it isn't a priviledged account, but still has the permissions it needs to read WMI namespaces for performance monitoring.

### Create your monitoring service account

This should be a no-brainer, but create your service account in accordance with whatever requirements you need (password rotation, OU location, etc).

Just name it something like `svc_<monitoring user>`. Where `<monitoring user>` is something you can identify.

### Create a GPO to add this user to local monitoring groups.

1. Leave the default domain policy alone.
2. Create a new GPO
3. Go to:  `Computer Configuration` > `Policies` > `Windows Settings` > `Security Settings`. Click on `Restricted Groups`. Right-click on `Restricted Groups` and select `Add Group`.
4. Select the desired domain group and click ok.
5. In the bottom portion of the new windows "this group is a member of": click on `add`.

Add your monitoring user to these groups:

1. Distributed COM Users
2. Event Log Readers
3. Performance Monitor Users
4. Performance Log Users

Once you've created your GPO and assigned it to the OU(s) where your servers are located, and the GPO has had time to replicate, go to your servers and do a `gpupdate` so that the monitoring user service account gets added to the local groups you specified in the GPO above.

### Set Component Services Permissions

1. Open the Component Services MMC on the server.  You can open this with `run` or just by typing this in the start menu search: `dcomcnfg.exe`
2. Expand `Console Root` > `Component Services` > `Computers`.
3. Right click on `My Computer` > Select `Properties`
4. Click on the `COM Security` tab.
5. Under `Launch and Activation Permissions` section, click on `Edit Limits`
6. Click `Add...` > Change location to the local computer (not your Active Directory)
7. Click `Advanced` > then click `Find Now`
8. Use `CNTL` + `left click` to select _both_ `Distributed COM Users` *AND* `Performance Monitor Users`. 
9. Click OK.
10. Click OK again.
11. Do this step for both local groups of `Distributed COM Users` and `Performance Monitor Users`: Place a check mark in all four boxes for `Local Launch`, `Remote Launch`, `Local Activation` and `Remote Activation`.
12. Click OK.
13. Click OK again.
14. Close Component Services MMC.

### Set WMI Namespace Permissions 

1. Open the WMI management MMC on the server by running `wmimgmt.msc` from the start menu or the `run` prompt.
2. Select `WMI Console (Local)`, right click and select `Properties`.
3. Select the `Security` tab > highlight `Root` > Click on `Security`.
4. Add both local groups of `Distributed COM Users` and `Performance Monitor Users` by clicking on `Add...` > Change location to the local computer (not your Active Directory). Same thing you did in step 6, 7, 8 above.
5. Select the following boxes for *each* `Distributed COM Users` and `Performance Monitor Users`: `Execute Methods`, `Enable Account` and `Remote Enable`.
6. Do this for both groups `Distributed COM Users` and `Performance Monitor Users`: Click `Advanced` > Select _respectively_ (do this for both groups), highlight the group > Click `Edit` > In the `Applies to:` drop down, select `This namespace and subnamespaces`.
7. Click OK.
8. Once you've done that for both groups, click OK until you're back to the WMI Control. Close the window.

### Enable Firewall Rules for WMI

1. Open the Advanced Firewall rules and navigate to `Inbound Rules`.
2. Find the following rules and simply `Enable` them: `Windows Management Instrumentation (ASync-in)`, `Windows Management Instrumentation (DCOM-In)` and `Windows Management Instrumentation (WMI-In)`.
3. Do the exact same for these two rules: `Windows Remote Management (HTTP-In)` and `Windows Remote Management (HTTP-In)`. Yes, they're the same name but with different `Remote Address`.

### Restart WMI and WSMan

1. Open the services MMC by running `services.msc` from the start menu or in the `run` prompt.
2. For _both_ services: `Windows Management Instrumentation` *AND* `Windows Remote Mangement`: click `restart` for each service.

This _should_ be all you need to give your active directory service account for monitoring the appropriate permissions needed to monitor all performance metrics without the need to be either a Domain Administrator or a local administrator.  Making your security team happy.