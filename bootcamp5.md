kubectl get deployments

The DESIRED state is showing the configured number of replicas

The CURRENT state show how many replicas are running now

The UP-TO-DATE is the number of replicas that were updated to match the desired (configured) state

The AVAILABLE state shows how many replicas are actually AVAILABLE to the users

### Scale up

kubectl scale deployments/kubernetes-bootcamp --replicas=4

### IPs of pods:

kubectl get pods -o wide
