### 1.Create Deployment yaml file for tomcat.

`#` `vi tomcat.yaml`

```
---
apiVersion: v1
kind: Namespace
metadata:
  name: my-namespace
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: tomcat-deployment
  namespace: my-namespace
spec:
  replicas: 1
  selector:
    matchLabels:
      app: tomcat
  template:
    metadata:
      labels:
        app: tomcat
    spec:
      containers:
      - name: tomcat
        image: tomcat:9.0
        ports:
        - containerPort: 8080
---
apiVersion: v1
kind: Service
metadata:
  name: tomcat-service
  namespace: my-namespace
spec:
  selector:
    app: tomcat
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
      nodePort: 30080
  type: NodePort
```
`#` `kubectl apply -f tomcat.yaml`

### 2.Verify connect to tomcat server.
`#` `kubectl get node -o wide`  
※Verify this server ip address.  
`#` `curl http://172.18.0.4:30080`  
※Verify reply messages from tomcat web server. 