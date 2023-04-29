`#` `vi create-deployment-nginx.yaml`

```
apiVersion: apps/v1 
kind: Deployment 
metadata: 
  name: sample-resource 
spec: 
  replicas: 3 
  selector: 
    matchLabels: 
      app: sample-app 
  template: 
    metadata: 
      labels: 
        app: sample-app 
    spec: 
      containers: 
      - name: nginx-container 
        image: nginx:1.16 
        resources: 
          requests: 
            memory: 1024Mi 
            cpu: 500m 
          limits: 
            memory: 2048Mi 
            cpu: 1000m 
--- 
apiVersion: v1 
kind: Service 
metadata: 
  name: sample-ld 
spec: 
  type: NodePort 
  ports: 
  - name: "http-port" 
    protocol: "TCP" 
    port: 8080 
    targetPort: 80 
    nodePort: 30080 
  selector: 
    app: sample-app
```
`#` `kubectl apply -f create-deployment-nginx.yaml`