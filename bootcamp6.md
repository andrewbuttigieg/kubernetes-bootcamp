### Updates application to version 2:

kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=jocatalin/kubernetes-bootcamp:v2

### Check upated:

kubectl get pods -o wide (will show new pods that are v2 and delete v1 pods)

curl $(minikube ip):$NODE_PORT (should show v2 now)

kubectl rollout status deployments/kubernetes-bootcamp (shows if the roll out was successful)

kubectl set image deployments/kubernetes-bootcamp kubernetes-bootcamp=gcr.io/google-samples/kubernetes-bootcamp:v10 (will fail)

### Rollback:

kubectl rollout undo deployments/kubernetes-bootcamp

### What is the scope of a rolling update?

To update a Deployment

Rolling updates allows Deployments update with zero downtime by incrementally updating Pods instances with new ones

### If a Deployment is exposed publicly, what happens with the network traffic during an update?

Is load-balanced only to available instances (old or new)

If a Deployment is exposed publicly, the Service will load-balance the traffic only to available Pods during the update

### What kubectl command can be used to do a Deployment update?

kubectl set image

"set image" can be used to update the image of an container
