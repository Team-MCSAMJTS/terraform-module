-Using terraform workspaces; to create an environment 

>> terraform workspace new dev               

// do this for stage & prod replacing "dev";It creates a forlder terraform.tfstate.d with all the three envs in it

-install "tree" to see what has been done as you go alone

- To switch to an environment for execution in it & for help with commands run
 $ terraform workspace -h
- You may want to do  git init when you switch into any env newly

- To enter any env e.g dev
> terraform workspace select dev            // you can do this for stage & prod replacing "dev"

- To see what environment you are at anytime 
> terraform workspace show

- Wwhen you apply the execution in the evvironment, it creates separate terraform.tfstate file for each env


BE VERY CAREFUL USING TERRAFORM WORKSPACE TO NOT DELETE AN ENV BY MISTAKE ENSURE YOU ARE IN THE DESIRED ENV

#NOTE 
- you can create different <file_name>.tfvars files for diffrent envs and pass it when running the commands for instance in dev env, if you create a dev.tfvars(where in it we have ami and instance_type defined with values) the command to run 
> treeaform apply -var-file=dev.tfvars.

 OR

- Use the method we are using now where env is declared in the instance_type variable and using lookup in the ec2_instance variable
- 'terraform.workspace' is a default that is picked for the env you are in when running your commands

terraform plan
terraform apply

