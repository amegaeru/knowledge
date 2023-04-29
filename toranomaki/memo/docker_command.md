## 1.Login
|details|command|
|:--|:--|
|Login the DockerHUB Web Site|# docker login -u <username> -p <password> <server>|
|Logout the DockerHUB Web Site|# docker logout <server>|

## 2.Managed Image
|details|command|
|:--|:--|
|Verify Docker Image|# docker image ls|
|Search Images|# docker search <imageName> --limit 50|
|Pull Image|# docker pull ubuntu|
|Push Image|# docker tag <imageID> <repository/imageName>|
||# docker push <repository/imageName>|

## 3.Pod
|details|command|
|:--|:--|
|Launch a Container|# docker run -it ubuntu|
|Launch a Container(Mount File)|# docker run -it ubuntu -v ${pwd}/mount.xtx:/var/run 0702|
|Verify launch a containers|# docker ps -a|
|Start a Container|# docker start <ContainerID>|
|Stop a Container|# docker stop <ContainerID>|



