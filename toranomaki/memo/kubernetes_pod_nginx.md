`#` `cat << EOF > app-nginx.yaml`

```
apiVersion: apps/v1
kind: Deployment
metadata:
  labels:
    app: web-nginx
  name: web-nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web-nginx
  template:
    metadata:
      labels:
        app: web-nginx
    spec:
      containers:
      - image: nginx
        name: nginx
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: web-nginx
spec:
  selector:
    app: web-nginx # このラベルを持つPodに振り分けを行う
  type: NodePort
  ports:
    - port: 80
      nodePort: 30080 # workerノードのIPで接続できるポート
EOF
```

`#` `kubectl create -f app-nginx.yaml`