kubectl get services<br />
### Exposes traffic on port 8080 to public:
kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080<br /> 
### NodePort is the public port 8080 is NATed to:
kubectl describe services/kubernetes-bootcamp<br />
export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')<br />
echo NODE_PORT=$NODE_PORT<br />
curl $(minikube ip):$NODE_PORT<br />
kubectl describe deployment<br />
### Get by label:
kubectl get pods -l run=kubernetes-bootcamp<br />
kubectl get services -l run=kubernetes-bootcamp<br />
### Add label:
export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')<br />
echo Name of the Pod: $POD_NAME<br />
kubectl label pod $POD_NAME app=v1<br />
### Delete service:
kubectl delete service -l run=kubernetes-bootcamp
