kubectl get deployments

The DESIRED state is showing the configured number of replicas

The CURRENT state show how many replicas are running now

The UP-TO-DATE is the number of replicas that were updated to match the desired (configured) state

The AVAILABLE state shows how many replicas are actually AVAILABLE to the users

### Scale up

kubectl scale deployments/kubernetes-bootcamp --replicas=4

### IPs of pods:

kubectl get pods -o wide

### Replicas:

kubectl describe services/kubernetes-bootcamp

### Load balancing

export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')

echo NODE_PORT=$NODE_PORT

curl $(minikube ip):$NODE_PORT (this will go to a different pod on each request)

### Scale down

kubectl scale deployments/kubernetes-bootcamp --replicas=2

### What is the link between Scaling and Deployments?

Scaling changes the number of replicas in a Deployment

### What parameter allows "kubectl run" command to scale Deployments?

--replicas

### What are the possible states of a Pod replica?

DESIRED, CURRENT, UP-TO-DATE or AVAILABLE
