# What is Kubernetes?

Kubernetes is a orchestration tool for microservices. It helps to scale the deployment services according to the need of the users.

# To manage the cloud native microservices we have to make sure some things

-> Scale on demand

-> Self-heal of deployment 
 
-> Support zero-downtime rolling updates

-> Run anywhere

And Kubernetes provides all of them. It is called the OS of the cloud.

# What that means is you don't have to worry which service you are using underneath. 

This can be AWS. You can just swap out the underlying architecture if you use Kubernetes. for Beginners with NodeJS Express Application that's why it's so popular and powerful.

# Cluster and Nodes

A Kubernetes cluster is a collection of machines that have kubernetes installed. The machines can be a computer, a VM, a raspberry PI and so on.

We can install kubernetes on the machines and connecting them creates a Kubernetes cluster. And each of the machines are called Nodes

# Master and Worker
There are 2 kinds of nodes.

1. Master nodes (Masters)
2. Worker nodes (Nodes)

# Masters

Masters host the control pane and Nodes host user applications. You want to maintain high availability for the master nodes.

# Workers
The Nodes (aka Workers) run 2 main services.

1. Kubelet
2. Container runtime

# Kubelet

The kubelet is the main kubernetes agent. It communicates with the control pane.

# Deploy a NodeJS application on a Kubernetes cluster

1. Create a Docker Image for a NodeJS application
2. ublish that Image to DockerHub
3. Create a Linode Kubernetes Cluster
4. Install Kubectl on our local machine
5. Deploy our application into Kubernetes cluster

# Install Docker  

By the help of docker documentation, We have install docker with the latest version.

* For root permission
sudo su

So let's clone it first!
* git clone https://github.com/johnpapa/node-hello.git

check the node-hello project cloned in the local machine
* ls
mv node-hello nodeapp

Now, login to the docker account
* docker login
* username
* password

# Build the docker image

* docker build -t samarthagarwal9/nodeapp .

to check the docker image
* docker images

# Run the Docker image at 3000 port
* docker run -d -p 3000:3000 samarthagarwal9/nodeapp
* docker ps

To config the IP at which the node-hello app deploy as a container 
* ip addr
* docker ps

Remove the container from the docker 
* docker rm -f container_id
* docker ps

# Push the Docker image to the Docker Hub 
* docker login 
* username:
* Password:
* docker push samarthagarwal9/nodeapp:latest

Docker successfully push the image which is conatinerized.
# Create Deployment and Service files on Kubernetes

Now, we have to create two YAML files.
1. Deployment.yml
2. Service.yml

* vi Deployment.yml 
* vi Service.yml

# Deploy the cluster on Kubernetes

Install MINIKUBE by the help of kubernetes docs.

To check the minikube status 
* minikube status

To start the pods on the cluster
* kubectl get pods 

To start the deployment 
* kubectl get deployment 
* kubectl get svc
* kubectl apply -f deployment.yml 
* kubectl get deployement
* kubectl get pods

To start the service on Kubernetes cluster
* kubectl apply -f service.yml
* kubectl get svc
* minikube service nodeapp-service

Ip generate at which the deployment of any application can be done 


* By following the abobe steps we successfully deploy the Node App on Kubernetes as well as on Docker!!!!.. 