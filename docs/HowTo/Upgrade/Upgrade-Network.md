description: Upgrade Pantheon     
<!--- END of page meta data -->

# Upgrading your Network 

We recommend: 

* Using an orchestration method (for example, Ansible or Chef) to keep all nodes in sync with your desired configuration. 
* Storing your configuration under version control. 

## Ansible 

The [Pantheon Ansible role on Galaxy](https://galaxy.ansible.com/pegasyseng/pantheon) can be used directly
or customised to suit your needs. Upgrade by running the play. The play: 

1. Stops Pantheon.
1. Downloads the updated version.
1. Applies any new configuration.
1. Starts Pantheon.

## Finding Peers on Restarting 

Nodes store known peers in the peer table. The peer table is not persisted to disk. When a node restarts, 
the node connects to the specified bootnodes and discover other nodes through the peer discovery process. 
The node continues collecting data from where it was (assuming there was no data corruption in a failure scenario). 

The node may also be connected to by other nodes that still have the restarted node in their peer table.
These nodes can also be used to discover other nodes but to ensure the restarted node successfully rejoins
the network ensure at least one operational bootnode is specified.



