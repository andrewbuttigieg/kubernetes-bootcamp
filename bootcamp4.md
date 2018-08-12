kubectl get services<br />
kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080<br /> 
kubectl describe services/kubernetes-bootcamp<br />
export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')<br />
echo NODE_PORT=$NODE_PORT<br />
curl $(minikube ip):$NODE_PORT<br />
kubectl describe deployment<br />
