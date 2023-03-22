**Init a new terraform project/configuration when targeting AWS**
```
mkdir my_new_configuration  
vi main.tf  
  
aws configure  
  
terraform init    
terraform plan  
terraform apply  
```

**How to name required providers?**  
The local name of the required providers should match the remote source.  
If not you have to assign a provider within the ressource. 

terraform plan will throw this warning  
`Provider "registry.terraform.io/hashicorp/aws" was implicitly required via resource "aws_instance.my_app_server", but listed in required_providers as "foo". Either the local name in required_providers must    
 match the resource name, or the "foo" provider must be assigned within the resource block."`

**Where to declare (input) variables?**
Variables can be declared anywhere in ones configuration but it's recommended to declare variables in a file called variables.tf  
https://developer.hashicorp.com/terraform/tutorials/configuration-language/variables  

**Whats the difference between NACLs (Network Access Lists) and Security Groups?**  
NACLs apply to Networks (Subnets), while Security Groups apply to EC2 instances AND AWS Services.  
State
* NACLs are stateless, which if you allow outgoing traffic from a network, you also have to allow the incoming traffic returning from these outgoing requests  
* Security Groups are stateful, if there is an outgoing rule defined, the returning traffic will be allowed as well (without an explicitly defined rule)  

See: https://gocloudtech.medium.com/aws-security-groups-vs-nacl-whats-the-difference-a38b9eb6796b  