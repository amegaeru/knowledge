`#` `vi create-namespace.yaml`
```
apiVersion: v1 
kind: Namespace 
metadata: 
  name: sample-namespace
```
`#` `kubectl apply -f create-namespace.yaml`