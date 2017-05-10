# Git & Github

#### create a local Git repository from a directory
git init

git config --global user.name "Your Name"
git config --global user.email you@example.com


##### tell git command to cache your credentials so you won't have to type them each time
git config --global credential.helper cache

##### add stuff to repo
git add -A

##### commit content
git commit -m changed

##### add a remote reference to deploy to (from local repo)

git remote add azure https://me@myserver.com:443/repo.git         

##### push local repo to azure app service
git push origin master


##### Delete *everything* on a remote Git repository

mkdir empty; cd empty

git init

touch test.txt

git add –A; git commit –m changed

git remote add origin <url>

git push --force --set-upstream origin master
