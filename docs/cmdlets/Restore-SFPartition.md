# Restore-SFPartition
Triggers restore of the state of the partition using the specified restore partition description.
## Description

Restores the state of a of the stateful persisted partition using the specified backup point. In case the partition is 
already being periodically backed up, then by default the backup point is looked for in the storage specified in 
backup policy. One can also override the same by specifying the backup storage details as part of the restore 
partition description in body. Once the restore is initiated, its progress can be tracked using the GetRestoreProgress 
operation. 
                In case, the operation times out, specify a greater restore timeout value in the query parameter.



## Required Parameters
#### -PartitionId

The identity of the partition.



#### -BackupId

Unique backup ID.



#### -BackupLocation

Location of the backup relative to the backup storage specified/ configured.



#### -ConnectionString

The connection string to connect to the Azure blob store.



#### -ContainerName

The name of the container in the blob store to store and enumerate backups from.



#### -Path

UNC path of the file share where to store or enumerate backups from.



## Optional Parameters
#### -FriendlyName

Friendly name for this backup storage.



#### -PrimaryUserName

Primary user name to access the file share.



#### -PrimaryPassword

Primary password to access the share location.



#### -SecondaryUserName

Secondary user name to access the file share.



#### -SecondaryPassword

Secondary password to access the share location



#### -RestoreTimeout

Specifies the maximum amount of time to wait, in minutes, for the restore operation to complete. Post that, the 
operation returns back with timeout error. However, in certain corner cases it could be that the restore operation 
goes through even though it completes with timeout. In case of timeout error, its recommended to invoke this operation 
again with a greater timeout value. the default value for the same is 10 minutes.



#### -ServerTimeout

The server timeout for performing the operation in seconds. This timeout specifies the time duration that the client 
is willing to wait for the requested operation to complete. The default value for this parameter is 60 seconds.



