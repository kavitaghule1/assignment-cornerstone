**<span style="font-size: 26px;">Gocalc Application </span>**
**<span style="font-size: 12px;">prerequesits</span>**


helm installed,
docker installed,
git installed,
miniqube / k8s cluster
 
To create a Helm chart for the go-calc repository and deploy it, follow these steps:

Clone the Repository: Clone the go-calc repository from GitHub to your local machine.

git clone https://github.com/edcast/go-calc.git

docker build -t gocalc .

docker tag gocalc kavighule6/gocalc:01

docker push kavighule6/gocalc:01

Initialize Helm: If you haven't already, initialize Helm on your local machine.

helm init

helm create go-calc

Package Helm Chart: Package the Helm chart into a .tgz file.

helm package go-calc

Install Helm Chart: Install the Helm chart onto your Kubernetes cluster.

helm install gocalc gocalc-0.1.0.tgz

Verify Installation: Verify that the go-calc application is deployed successfully.

helm status gocalc

kubectl get pods

kubectl get services
#minikube ssh 
#curl http://localhost:30580

#curl http://minikube_ip:8080/health


