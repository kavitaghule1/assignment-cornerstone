# MySQL Database Setup and Usage Guide

This guide provides instructions on setting up a MySQL database and connecting to it via a local client. Additionally, it demonstrates how to run queries on test data that has been inserted into the database.

## Prerequisites

Before getting started, ensure you have the following prerequisites installed:
- MySQL Server
- MySQL Client (such as MySQL Workbench or MySQL Command Line Client)

## Installation

1. Install MySQL Server on your local machine. You can download MySQL Community Server from the official website: [MySQL Downloads](https://dev.mysql.com/downloads/).

2. Follow the installation instructions provided for your operating system.

3. Once MySQL Server is installed, start the MySQL service.

## Usage

### Connecting to MySQL Server

1. Open your MySQL client application (e.g., MySQL Workbench).

2. Create a new connection using the following credentials:
   - Host: localhost
   - Port: 3306 (default MySQL port)
   - Username: root
   - Password: [your_mysql_root_password].




# MySQL Helm Chart

This Helm chart deploys a MySQL database in a Kubernetes cluster.

## Prerequisites

Before you begin, ensure you have the following installed:

- Helm: Follow the [Helm installation instructions](https://helm.sh/docs/intro/install/) to install Helm on your machine.
- Kubernetes: Set up a Kubernetes cluster. You can use Minikube, kind, or any other Kubernetes distribution.

## Installation

cd mysql-chart

#Install the MySQL Helm chart:

helm create mysql

#give confirutation
#Modify the values.yaml file in the mysql directory to configure MySQL settings such as database name, username, password, etc.
#Adjust the templates/deployment.yaml file to define the MySQL deployment according to your requirements.

helm package .

helm install mysql ./mysql

#Accessing MySQL

#Once the MySQL deployment is up and running, you can access it using a MySQL client such as MySQL Workbench or the mysql command-line tool.
#Use the Kubernetes service associated with the MySQL deployment to connect to the database.

### Connecting to MySQL Server

kubectl exec -it <mysql-pod-name> -- mysql -u<username> -p<password> <database-name>

CREATE DATABASE my_database;

USE DATABASE my_database;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO users (username, email) VALUES ('john_doe', 'john@example.com');

INSERT INTO users (username, email) VALUES ('jane_doe', 'jane@example.com');

SELECT * FROM users;

SELECT username, email FROM users WHERE id = 1;

Clean Up
To uninstall the MySQL deployment, run the following command:

helm uninstall mysql
