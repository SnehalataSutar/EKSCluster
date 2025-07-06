## Create EKS cluster with 2 nodes using terraform

### Step 1: Prerequisites
Ensure you have:

•	AWS account with IAM permissions for EKS, VPC, IAM, EC2.

•	AWS CLI configured with aws configure.

•	Terraform installed.

•	kubectl installed.

### Project Structure

•	eks-terraform/

•	├── main.tf

•	├── variables.tf

•	└── outputs.tf

Write the code from main.tf, variable.tf and outputs.tf

### Step 2: Deploy

#### 🔧 Installing Terraform

``` sudo apt-get update 

sudo apt-get install -y gnupg software-properties-common curl

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

sudo apt-get update

sudo apt-get install terraform 

terraform -v 

terraform init

terraform plan

terraform apply


#### After apply, run:

$ aws eks --region <region_name> update-kubeconfig --name my-eks-cluster(Cluster_name)

$ kubectl get nodes

You should see 2 worker nodes ready.




