```
# kubectl create configmap war-files --from-file=/tmp/sample.war -n my-namespace
# vi tomcat.yaml
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
        volumeMounts:
        - name: war-file
          mountPath: /usr/local/tomcat/webapps
      volumes:
      - name: war-file
        configMap:
          name: war-files
# kubectl apply -f tomcat.yaml
# kubectl exec -it [tomcat_container] -- /bin/bash
[tomcat_container]# cd /usr/local/tomcat/webapps
[tomcat_container]# ls 
sample.war

```

http://[nodeIP]:[nodePort]/sample
<br>
<br>
### Example:
http://172.18.0.4:30080/sample