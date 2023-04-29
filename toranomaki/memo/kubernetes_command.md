### Verify:
|details|command|
|:--|:--|
|Verify Node IP Address|# kubectl get node -o wide|
|Verify PodList|# kubectl get pod -n [namespace]|
|Verify Service|# kubectl get service|

### Connection:
|details|command|
|:--|:--|
|Connect Pods|# kubectl exec -it [podName] -- /bin/bash|

### jsonpath:
|details|command|
|:--|:--|
|Verify jsonpath|# kubectl get pod [podname] -o jsonpath='{.metadata.labels}'|

### apply:
|details|command|
|:--|:--|
|Apply from Local manifest file|# kubectl apply -f test.yaml|
|Apply from github|# kubectl apply -f https://raw.githubusercontent.com/amegaeru/template/main/01.kubernetes/test.yaml|
 
