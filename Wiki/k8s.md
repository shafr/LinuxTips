Copy secrets between namespaces:
```
kubectl get secret secret1 --namespace=test -o yaml | sed 's/namespace: test/namespace: test1/g' | kubectl create -f -  
```

Change context:
```
kubectl config set-context --current --namespace=ggckad-s2
```
