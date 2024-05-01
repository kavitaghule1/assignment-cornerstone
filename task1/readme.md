**<span style="font-size:68px;"><b> Assignment Cornerstone:</b></span>**

**<span style="font-size:24px;">LocalStack Project</span>**

#This project demonstrates how to use LocalStack to emulate AWS services locally, specifically focusing on creating an API Gateway.

**<span style="font-size:24px;">Prerequisites</span>**

#Before running this project, ensure you have the following dependencies installed:

Docker: Install Docker

Docker Compose: Install Docker Compose

Terraform: Install Terraform

Git: Install Git

Java: Install Java

Setup Instructions
##Follow these steps to set up and run the LocalStack project:

**Clone the repository:**

git clone https://github.com/localstack/localstack
#Navigate to the project directory:

cd localstack

#Start LocalStack using Docker Compose:

docker-compose up -d
#Verify that LocalStack is running:

docker ps
#Once LocalStack is running, you can use it to create and test AWS resources locally.

#Creating an API Gateway and Apply the Terraform configuration to create the API Gateway resources:
**#Initialize Terraform:**

terraform init

#Validate the Terraform configuration:

terraform validate

#Apply the Terraform configuration:

terraform apply --auto-approve

#Once Terraform has applied the configuration successfully, it will output the endpoint URL of the API Gateway.

#Use CURL or any HTTP client to test the API Gateway:


curl -X GET http://localhost:4566/restapis/<API_ID>/

#Replace <API_ID> with the actual API ID obtained from the Terraform output.

**Cleanup**
#After you have finished using the LocalStack project, you can clean up the resources by stopping and removing the Docker containers:

docker-compose down
