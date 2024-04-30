
# assignment-cornerstone
LocalStack Project
This project demonstrates how to use LocalStack to emulate AWS services locally, specifically focusing on creating an API Gateway.

Prerequisites
Before running this project, ensure you have the following dependencies installed:

Docker: Install Docker
Docker Compose: Install Docker Compose
terraform : Install terraform
git: Install git
java: Install java
#Setup Instructions:
#Follow these steps to set up and run the LocalStack project:
Clone the repository:
git clone https://github.com/localstack/localstack
Navigate to the project directory:
cd localstack

Start LocalStack using Docker Compose:
docker-compose up -d //Verify that LocalStack is running 
docker ps
Once LocalStack is running, you can use it to create and test AWS resources locally. 

#Creating an API Gateway
#Apply the Terraform configuration to create the API Gateway resources:

terraform init
terraform apply   //Once Terraform has applied the configuration successfully, it will output the endpoint URL of the API Gateway.

#Use CURL or any HTTP client to test the API Gateway:
curl <endpoint-url>/example    //Replace <endpoint-url> with the actual endpoint URL obtained from the Terraform output.
Cleanup
#After you have finished using the LocalStack project, you can clean up the resources by stopping and removing the Docker containers:
docker-compose down
