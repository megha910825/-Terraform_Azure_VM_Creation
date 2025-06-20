### Steps to provision a VM in azure via Terraform

- Clone this repository
- Create a free subscription account in azure
- install azure cli on local
- do azure login via az login
- Install Terraform if it is not installed already
- intialize the Terraform deployment via following command
  ```
     terraform init -upgrade
  ```
- Run terraform plan to create an execution plan
  ```
     terraform plan -out main.tfplan
  ```
- Run terraform aply to apply the execution plan to your cloud infrastructure
   ```
   terraform apply main.tfplan
   ```
- Run the following command to get the VM's public IP address and make note of it:
  ```
  echo $(terraform output -raw public_ip_address)
  ```
- Access the webpage on port 80 with the output IP
- Now to clean up the resources , run terraform plan and sepcify the destroy flag
  ```
   terraform plan -destroy -out main.destroy.tfplan
  ```
- Run terraform apply to apply the destroy execution plan.
  ```
    terraform apply main.destroy.tfplan
  ```

   
