1. create a local git repo
```
$git init /tmp/rebase-sandbox
Initialized empty Git repository in /tmp/rebase-sandbox/.git/
$cd /tmp/rebase-sandbox/
```

2. create a local master branch via initial commit  
```
$git commit --allow-empty -m "initial commit"
[master (root-commit) e8fa4d3] initial commit
$git branch -a
* master
```
3. ammend a recent commit  
> git -a == git add .  
```
$echo 'hello Linux' > greeting.txt 
$git commit -a --amend 
[master c35d191] change greeting.txt to hello Linux
 Date: Tue Feb 16 22:04:39 2021 -0500
 1 file changed, 1 insertion(+)
 create mode 100644 greeting.txt
$git log --oneline
c35d191 (HEAD -> master) change greeting.txt to hello Linux
e8fa4d3 initial commit
```
