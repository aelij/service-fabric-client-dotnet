# Remove-SFNodeState
Notifies Service Fabric that the persisted state on a node has been permanently removed or lost.
## Description

This implies that it is not possible to recover the persisted state of that node. This generally happens if a hard 
disk has been wiped clean, or if a hard disk crashes. The node has to be down for this operation to be successful. 
This operation lets Service Fabric know that the replicas on that node no longer exist, and that Service Fabric should 
stop waiting for those replicas to come back up. Do not run this cmdlet if the state on the node has not been removed 
and the node can come back up with its state intact.



