


```sh
git init
git add --all
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/SagarMhatre/mcquery-kong-k8s.git
git push -u origin main
```
```sh

kubectl config get-contexts
cat ~/.kube/config

helm repo add kong https://charts.konghq.com
helm repo update

clear
cd /Users/sagarmhatre/Documents/src/mcquery/kong-k8s
kubectl apply -f kong.yaml

# clear
NAMESPACE=kong
kubectl get deployments --namespace=$NAMESPACE
kubectl get pods --namespace=$NAMESPACE
kubectl get services --namespace=$NAMESPACE

POD_NAME=$(kubectl get pods --namespace=$NAMESPACE --no-headers -o custom-columns=":metadata.name")
POD_NAME=kong-migrations-cp76q 
kubectl describe pod $POD_NAME --namespace=$NAMESPACE
kubectl logs $POD_NAME --namespace=$NAMESPACE

kubectl delete pod $POD_NAME --namespace=$NAMESPACE


# Stop All
clear
cd /Users/sagarmhatre/Documents/src/mcquery/eks-kong
kubectl delete -f kong.yaml

```