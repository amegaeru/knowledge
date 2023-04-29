## 1.Command Cheat Sheet
|details|command|
|:--|:--|
|Create Cluster|# eksctl create cluster --name my-cluster --region ap-northeast-1|
|Upgrade Cluster|# eksctl upgrade cluster --name my-cluster --version 1.25 --approve|
|Verify Cluster|# eksctl get cluster|
|Delete Cluster|# eksctl delete cluster --name my-cluster --region ap-northeast-1|
|Upgrade Nodegroup|# eksctl upgrade nodegroup --name=my-nodegroup --cluster=my-cluster --region ap-northeast-1|

