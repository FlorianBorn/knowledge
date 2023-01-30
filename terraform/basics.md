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