# Disable-SFApplicationBackup
Disables periodic backup of Service Fabric application.
## Description

Disables periodic backup of Service Fabric application which was previously enabled.



## Required Parameters
#### -ApplicationId

The identity of the application. This is typically the full name of the application without the 'fabric:' URI scheme.
                    Starting from version 6.0, hierarchical names are delimited with the "~" character.
                    For example, if the application name is "fabric:/myapp/app1", the application identity would be 
"myapp~app1" in 6.0+ and "myapp/app1" in previous versions.



#### -CleanBackup

Boolean flag to delete backups. It can be set to true for deleting all the backups which were created for the backup 
entity that is getting disabled for backup.



