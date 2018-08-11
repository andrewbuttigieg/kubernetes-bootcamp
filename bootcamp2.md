Create deployment:<br />
kubectl run kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --port=8080<br />
<br />
List deployment:<br />
kubectl get deployments<br />
<br />
kubectl proxy<br />
<br />
Get pod name:<br />
export POD_NAME=$(kubectl get pods -o go-template --template '{{range .items}}{{.metadata.name}}{{"\n"}}{{end}}')
echo Name of the Pod: $POD_NAME<br />

