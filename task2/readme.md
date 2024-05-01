**<span style="font-size: 20px;">gocalc</span>**

prerequesits
helm installed
docker installed
git installed
miniqube / k8s cluster
 
To create a Helm chart for the go-calc repository and deploy it, follow these steps:

Clone the Repository: Clone the go-calc repository from GitHub to your local machine.

git clone https://github.com/edcast/go-calc.git

docker build -t mygoapp .

docker tag mygoapp kavighule6/mygoapp:v1

docker push kavighule6/mygoapp:v1

Initialize Helm: If you haven't already, initialize Helm on your local machine.

helm init

cd go-calc

mkdir helm-chart

helm create go-calc

Package Helm Chart: Package the Helm chart into a .tgz file.

helm package helm-chart

Install Helm Chart: Install the Helm chart onto your Kubernetes cluster.

helm install go-calc ./go-calc-0.1.0.tgz
Verify Installation: Verify that the go-calc application is deployed successfully.

kubectl get pods
kubectl get services
curl http://<service-ip>:<service-port>
