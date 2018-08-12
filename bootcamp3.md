kubectl get pods<br />
kubectl describe pods<br />
export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')<br />
kubectl logs $POD_NAME<br />
kubectl exec $POD_NAME env<br />
kubectl exec -ti $POD_NAME bash<br />
