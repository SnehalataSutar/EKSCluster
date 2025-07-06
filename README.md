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
```

#### 🛠️ Installing kubectl

```
curl -LO "https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
kubectl version --client
```

#### Install AWS CLI on Ubuntu

Run the following:
```
sudo apt update
sudo apt install -y awscli
```

Then verify it's installed:

```
aws --version
```


#### After apply, run:

```
$ aws eks --region us-east-1(region_name) update-kubeconfig --name my-eks-cluster(Cluster_name)
```
```
$ kubectl get nodes
```
You should see 2 worker nodes ready.

![Screenshot (151)](https://github.com/user-attachments/assets/23ee6a63-e674-47c0-81be-1b9e445feebb)

![Screenshot (152)](https://github.com/user-attachments/assets/2502974d-10e8-4fbb-a933-fc167a7227e5)

![Screenshot (153)](https://github.com/user-attachments/assets/69e88d2e-018c-4918-9897-7dc684fe9625)





