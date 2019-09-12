description: Configuring validators in production networks    
<!--- END of page meta data -->

# Configuring Validators in a Production Network 

In the same way as when creating bootnodes:  
1. Create the node key pair (that is, the private and public key) before starting the validator and put
the private key in the `/opt/besu` directory.
1. When creating validators in the cloud (for example, AWS, Azure), attempt to assign a static IP to them. 
If your network is: 
* Publicly accessible, assign an elastic IP. 
* Internal only, specify a private IP address when you create the instance and record of this IP. 

We recommend validator configuration is kept under source control. 

Ensure you allow for redundancy. The following formuala defines the number of faulty validators that can be tolerated when
using IBFT 2.0:

`f = (n-1)/3` 

Where:
* f = number of faulty validators
* n = number of validators 

## Adding and Removing Validators

In operating networks, validators are voted in or out of the pool. If you are adding a Validator that is also operating as a Bootnode, please follow the steps outlined above in the Bootnodes section. 
Validators are generally removed because of errors or a lack of trust. In the event that you are pulling out a Validator that is also a Bootnode, please ensure that are enough Bootnodes on the network.

## Validators as Bootnodes 

Validators can also be bootnodes. Other than the [usual configuration for bootnodes](Bootnodes.md) no additional configuration
is required when a validator is also a bootnode. 

If a validator is removed that is also a bootnode, ensure there are enough remaining bootnodes on the 
network. 

