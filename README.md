# angular-django-docker-starter-k8s-config


# Get started with minikube
minikube is a VM that lets you create kubernetes node(only master node) in your local machine.

### start minikube
`minikube start` 

### Set docker env
set this command for every ternimal you are working with minikube.
`eval $(minikube docker-env)`

this lets you use minikube docker registry instead of your local docker registry in your working terminal. which means, you can build your docker image locally and register it to minikube docker registry. this allows you to use your docker image for kubernetes without registering the image to docker hub. make sure to above command is enable on `your working terminal`.

### build your image
- `docker build -t IMAGE_NAME` .
 



# kubectl

kubectl is CLI for kubernetes cluster. 

## Basic commands
- apply
`apply` manages applications through files defining Kubernetes resources. It creates and updates resources in a cluster through running `kubectl apply`.
	- `kubectl apply -f your-deployment.yaml`

- get 
list given kubernetes recource. kubernetes only shows the recources in default namespace. 
	-	`kubectl get services/pods/deployment/event/ns`

	list given kubernetes recource by namespace
	-	`kubectl get services/pods/deployment/event -n=<your_namespace>`

- edit 
update kubernetes config. 
	-	`kubectl edit services/pods/deployment/event.yaml`



## debug

check the log of a pod
- `kubectl logs -f <pod_name> -n=<your_namespace>`

show events
- `kubectl get events`

