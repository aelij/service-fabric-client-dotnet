# New-SFApplicationUpgrade
Starts rolling back the currently on-going upgrade of an application in the Service Fabric cluster.
## Description

Starts rolling back the current application upgrade to the previous version. This API can only be used to roll back 
the current in-progress upgrade that is rolling forward to new version. If the application is not currently being 
upgraded use StartApplicationUpgrade API to upgrade it to desired version, including rolling back to a previous 
version.



