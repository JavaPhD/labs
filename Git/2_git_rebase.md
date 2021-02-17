## ammend a older commit  
1. add a new commit
```
$echo 'goodbye world' > farewell.txt
$git add .
$git commit -m "add farewell.txt"
[master 3230302] add farewell.txt
 1 file changed, 1 insertion(+)
 create mode 100644 farewell.txt
$git log --oneline
3230302 (HEAD -> master) add farewell.txt
c35d191 change greeting.txt to hello Linux
e8fa4d3 initial commit
```
2. amend greeting.txt and commit
```
$echo 'hello world' > greeting.txt 
$git commit -a -m "fix greeting.txt"
[master f19df2b] fix greeting.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
```
3. git log --oneline
```
$git log --oneline
f19df2b (HEAD -> master) fix greeting.txt
3230302 add farewell.txt
c35d191 change greeting.txt to hello Linux
e8fa4d3 initial commit
```
4. git rebase -i HEAD~3
```
pick c35d191 change greeting.txt to hello Linux
fixup f19df2b fix greeting.txt
pick 3230302 add farewell.txt
```
5. we "combined" the 2 commits of greeting.txt into one commit
```
$git log --oneline
a09e57e (HEAD -> master) add farewell.txt
97cf6a7 change greeting.txt to hello Linux
e8fa4d3 initial commit
```

