
# Deploy AWS Cloud Insfrastucture

A brief description of what this project does and who it's for

Step 1: Install terraform On the server

1.Using aws management console launch server.

2.visit https://www.terraform.io/ and click the download button.

3.select Linux amd64 and copy the link address.

4.Paste on the server wget https://releases.hashicorp.com/terraform/1.3.4/terraform_1.3.4_linux_amd64.zip

5. Install unzip package in server.

        sudo apt install unzip -y

6. Unzip terraform.

        sudo unzip terraform_1.3.4_linux_amd64.zip

7. copy terraform bin folder

        sudo cp terraform /bin
8. check terraform version

        terraform -v

step 2: Build Infrastructure
1. Install AWS CLI

        sudo apt-get -install awscli

2. Configure AWS CLI in your machine.

        aws configure

AWS Access Key ID [None]:AKIA2MLDJC55S6JNNN66

AWS Secret Access Key [None]: GO7JN5Yc+KtssOb661EtQB6Q03wUSbcPo38LfeuV

Default region name [None]: us-east-1

Default output format [None]:

Setp 3: Write Configuration:

1.Create a new file

        touch example.tf

example.tf
```terraform
provider "aws" {
    profile = "default"
    region = "us-east-1"

}

resource "aws_instance" "eaxmple" {
    ami ="ami-0c7217cdde317cfec"
    instance_type = "t2.micro"
}
```
2. Initialize 

        terraform init
3. Formate and validate the configuration
```
terraform fmt
```
```
terraform validate
```
4. Create insfrastructure
```
terraform apply 
```
```
terraform show
```