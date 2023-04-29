### Initialization:			
```
# git config --global user.name "UserName"
# git config --global user.email "MailAddress"
# git config --list
# git config user.name
# git config user.email
```

### Set up a Repository:
```
# md <localRepositoryFolder>
# cd <localRepositoryFolder>
# git init
# git remote add origin git@github.com/amegaeru/template.git
# git clone https://github.com/amegaeru/template.git
```

### Git Commit and push:
```
# cd <localRepositoryFolder>
# git add .
# git commit -m <message>
# git push
```

### Any Command:
|details|command|
|:--|:--|
|Verify Repository|# git remote -v|
|Verify Repository File List|# git ls-tree --name-only -r origin/main|
|Download Files to git|# curl -LO [URL]|
|Synchronization Remote|# git reset --hard origin/main|

 
