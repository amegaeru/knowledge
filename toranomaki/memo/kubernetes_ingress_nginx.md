
`#` `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.0.4/deploy/static/provider/cloud/deploy.yaml`
<br>
https://kubernetes.github.io/ingress-nginx/deploy/#docker-desktop
<br>  
`#` `vi create-ingress.yaml`  
<br>

```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp
spec:
  ingressClassName: "nginx"
  rules:
  - http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: myapp-service
            port:
              number: 80
```

<br>
`#` `kubectl apply -f create-ingress.yaml`  
<br>

```
# POD_NAMESPACE=ingress-nginx
# POD_NAME=$(kubectl get pods -n $POD_NAMESPACE -l app.kubernetes.io name=ingress-nginx --field-selector=status.phase=Running -o name)
# kubectl exec $POD_NAME -n $POD_NAMESPACE -- /nginx-ingress-controller --version
```
<br>
```
# kubectl get -n ingress-nginx service,deployment,pod
```

