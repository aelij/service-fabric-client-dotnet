# Resume-SFApplicationUpgrade
Resumes upgrading an application in the Service Fabric cluster.
## Description

Resumes an unmonitored manual Service Fabric application upgrade. Service Fabric upgrades one upgrade domain at a 
time. For unmonitored manual upgrades, after Service Fabric finishes an upgrade domain, it waits for you to call this 
API before proceeding to the next upgrade domain.



## Required Parameters
#### -ApplicationId

The identity of the application. This is typically the full name of the application without the 'fabric:' URI scheme.
                    Starting from version 6.0, hierarchical names are delimited with the "~" character.
                    For example, if the application name is "fabric:/myapp/app1", the application identity would be 
"myapp~app1" in 6.0+ and "myapp/app1" in previous versions.



#### -UpgradeDomainName

The name of the upgrade domain in which to resume the upgrade.



