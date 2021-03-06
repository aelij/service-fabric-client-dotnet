# Update-SFClusterUpgrade
Update the upgrade parameters of a Service Fabric cluster upgrade.
## Description

Update the upgrade parameters used during a Service Fabric cluster upgrade.



## Optional Parameters
#### -UpgradeKind

The type of upgrade out of the following possible values. Possible values include: 'Invalid', 'Rolling', 
'Rolling_ForceRestart'



#### -ForceRestart

If true, then processes are forcefully restarted during upgrade even when the code version has not changed (the 
upgrade only changes configuration or data).



#### -ReplicaSetCheckTimeoutInMilliseconds

The maximum amount of time to block processing of an upgrade domain and prevent loss of availability when there are 
unexpected issues. When this timeout expires, processing of the upgrade domain will proceed regardless of availability 
loss issues. The timeout is reset at the start of each upgrade domain. Valid values are between 0 and 42949672925 
inclusive. (unsigned 32-bit integer).



#### -FailureAction

The compensating action to perform when a Monitored upgrade encounters monitoring policy or health policy violations.
                    Invalid indicates the failure action is invalid. Rollback specifies that the upgrade will start 
rolling back automatically.
                    Manual indicates that the upgrade will switch to UnmonitoredManual upgrade mode.
                    . Possible values include: 'Invalid', 'Rollback', 'Manual'



#### -HealthCheckWaitDurationInMilliseconds

The amount of time to wait after completing an upgrade domain before applying health policies. It is first interpreted 
as a string representing an ISO 8601 duration. If that fails, then it is interpreted as a number representing the 
total number of milliseconds.



#### -HealthCheckStableDurationInMilliseconds

The amount of time that the application or cluster must remain healthy before the upgrade proceeds to the next upgrade 
domain. It is first interpreted as a string representing an ISO 8601 duration. If that fails, then it is interpreted 
as a number representing the total number of milliseconds.



#### -HealthCheckRetryTimeoutInMilliseconds

The amount of time to retry health evaluation when the application or cluster is unhealthy before FailureAction is 
executed. It is first interpreted as a string representing an ISO 8601 duration. If that fails, then it is interpreted 
as a number representing the total number of milliseconds.



#### -UpgradeTimeoutInMilliseconds

The amount of time the overall upgrade has to complete before FailureAction is executed. It is first interpreted as a 
string representing an ISO 8601 duration. If that fails, then it is interpreted as a number representing the total 
number of milliseconds.



#### -UpgradeDomainTimeoutInMilliseconds

The amount of time each upgrade domain has to complete before FailureAction is executed. It is first interpreted as a 
string representing an ISO 8601 duration. If that fails, then it is interpreted as a number representing the total 
number of milliseconds.



#### -ConsiderWarningAsError

Indicates whether warnings are treated with the same severity as errors.



#### -MaxPercentUnhealthyNodes

The maximum allowed percentage of unhealthy nodes before reporting an error. For example, to allow 10% of nodes to be 
unhealthy, this value would be 10.
                    
                    The percentage represents the maximum tolerated percentage of nodes that can be unhealthy before 
the cluster is considered in error.
                    If the percentage is respected but there is at least one unhealthy node, the health is evaluated 
as Warning.
                    The percentage is calculated by dividing the number of unhealthy nodes over the total number of 
nodes in the cluster.
                    The computation rounds up to tolerate one failure on small numbers of nodes. Default percentage is 
zero.
                    
                    In large clusters, some nodes will always be down or out for repairs, so this percentage should be 
configured to tolerate that.



#### -MaxPercentUnhealthyApplications

The maximum allowed percentage of unhealthy applications before reporting an error. For example, to allow 10% of 
applications to be unhealthy, this value would be 10.
                    
                    The percentage represents the maximum tolerated percentage of applications that can be unhealthy 
before the cluster is considered in error.
                    If the percentage is respected but there is at least one unhealthy application, the health is 
evaluated as Warning.
                    This is calculated by dividing the number of unhealthy applications over the total number of 
application instances in the cluster, excluding applications of application types that are included in the 
ApplicationTypeHealthPolicyMap.
                    The computation rounds up to tolerate one failure on small numbers of applications. Default 
percentage is zero.



#### -ApplicationTypeHealthPolicyMap

Defines a map with max percentage unhealthy applications for specific application types.
                    Each entry specifies as key the application type name and as value an integer that represents the 
MaxPercentUnhealthyApplications percentage used to evaluate the applications of the specified application type.
                    
                    The application type health policy map can be used during cluster health evaluation to describe 
special application types.
                    The application types included in the map are evaluated against the percentage specified in the 
map, and not with the global MaxPercentUnhealthyApplications defined in the cluster health policy.
                    The applications of application types specified in the map are not counted against the global pool 
of applications.
                    For example, if some applications of a type are critical, the cluster administrator can add an 
entry to the map for that application type
                    and assign it a value of 0% (that is, do not tolerate any failures).
                    All other applications can be evaluated with MaxPercentUnhealthyApplications set to 20% to 
tolerate some failures out of the thousands of application instances.
                    The application type health policy map is used only if the cluster manifest enables application 
type health evaluation using the configuration entry for HealthManager/EnableApplicationTypeHealthEvaluation.



#### -EnableDeltaHealthEvaluation

When true, enables delta health evaluation rather than absolute health evaluation after completion of each upgrade 
domain.



#### -MaxPercentDeltaUnhealthyNodes

The maximum allowed percentage of nodes health degradation allowed during cluster upgrades. The delta is measured 
between the state of the nodes at the beginning of upgrade and the state of the nodes at the time of the health 
evaluation. The check is performed after every upgrade domain upgrade completion to make sure the global state of the 
cluster is within tolerated limits. The default value is 10%.



#### -MaxPercentUpgradeDomainDeltaUnhealthyNodes

The maximum allowed percentage of upgrade domain nodes health degradation allowed during cluster upgrades. The delta 
is measured between the state of the upgrade domain nodes at the beginning of upgrade and the state of the upgrade 
domain nodes at the time of the health evaluation. The check is performed after every upgrade domain upgrade 
completion for all completed upgrade domains to make sure the state of the upgrade domains is within tolerated limits. 
The default value is 15%.



#### -ApplicationHealthPolicyMap

The wrapper that contains the map with application health policies used to evaluate specific applications in the 
cluster.



#### -ServerTimeout

The server timeout for performing the operation in seconds. This timeout specifies the time duration that the client 
is willing to wait for the requested operation to complete. The default value for this parameter is 60 seconds.



