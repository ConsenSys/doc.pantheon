description: Upgrade Pantheon     
<!--- END of page meta data -->

# Upgrading your Network 

We recommend: 
* Using an orchestration method (for example, Ansible or Chef) to keep all nodes in sync with your desired configuration
* Keeping your configuration under version control. 

We have an [Ansible Galaxy role](https://galaxy.ansible.com/pegasyseng/pantheon) that can be used directly
or customised to suit your needs. If using the role, ugrade by running the play. The play: 
1. Stops Pantheon
1. Downloads the updated version
1. Applies any new configuration
1. Starts Pantheon.

## Finding Peers on Restarting 

Nodes store known peers in the peer table. The peer table is not persisted to disk. When a node restarts, 
the default behaviour is to connect to the specified bootnodes and discover other nodes through the 
peer discovery process. The node will continue collecting data from where it was (assuming there was no data corruption in a failure scenario). 

The node may also be connected to by other nodes that still have the restarted node in their peer table.
These nodes can also be used to discover other nodes but to ensure the restarted node successfully rejoins
the network ensure at least one operational bootnode is specified.



