description: Configuring bootnodes in production networks    
<!--- END of page meta data -->

# Configuring Bootnodes in a Production Network 

A network must have at least one operating bootnode. To allow for continuity in the event of failure, 
we recommend having more than one bootnode. 

We do not recommend putting bootnodes behind a load balancer. We recommend putting more bootnodes on the network itself. 

The enode of a bootnode is tied to the node public key and IP address. The following steps simplify recovering
from complete bootnode failure: 

1. Create the node key pair (that is, the private and public key) before starting the bootnode and put
the private key in the `/opt/besu` directory.
1. When creating bootnodes in the cloud (for example, AWS, Azure), attempt to assign a static IP to them. 
If your network is: 
* Publicly accessible, assign an elastic IP. 
* Internal only, specify a private IP address when you create the instance and record of this IP. 

We recommend bootnode configuration is stored under source control. 

## Specifying Bootnodes 

We recommend you specify all bootnodes on the command line (even to the bootnodes themselves) to allow for failure. 

!!! example 
    If your network has 2 bootnodes, pass the following parameter all nodes including the bootnodes. 

   `--bootnodes=enode://eb5fe0417d5e59a8a52134bcf924a326bc86e0abf9083e3a2100a25b2bdc1cc41f19e29fc041a1444aec4dbdc2d327ccd54a97c2ef46cec3b5acc7414a009361@10.0.0.100:30303,hkjuu3bys9ilmjs2zkhvl8nrm0r9ugxzyxu1rkolxbq9l7nfeqqgmww6uxoxtk7axmuuch7qsrymddyuh3c6hg70xuwswk1mw3x0y4li5n5w2skfp1k4qktbuibswj46@10.0.1.101:30303`

## Adding and Removing Bootnodes 

Adding new bootnodes is a similar process to creating bootnodes. Once the bootnodes are created and added to the network,
update the `--bootnodes` command line option for each node to include the new bootnodes. 

Running nodes don’t need to be restarted. Updating the `--bootnodes` option means the next time they are 
restarted (for example, when running an update), they will use the new bootnodes.  
