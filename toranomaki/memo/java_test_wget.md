```
# kubectl exec -it [tomcat_containerName] -- /bin/bash
[tomcat_container]# cd /usr/local/tomcat/webapps
[tomcat_container]# wget http://tomcat.apache.org/tomcat-8.5-doc/appdev/sample/sample.war
[tomcat_container]# ls 
sample.war

```

http://[nodeIP]:[nodePort]/sample
<br>
<br>
### Example:
http://172.18.0.4:30080/sample