1. create a branch called squash
```
$git checkout -b squash
Switched to a new branch 'squash'
$git branch -a
  master
* squash
```

2. add many commits
```
$for c in H e l l o , ' ' w o r l d; do
> echo "$c" >> squash.txt
> git add squash.txt
> git commit -m "Add '$c' to squash.txt"
> done
[squash e87e4aa] Add 'H' to squash.txt
 1 file changed, 1 insertion(+)
 create mode 100644 squash.txt
[squash 008b474] Add 'e' to squash.txt
 1 file changed, 1 insertion(+)
[squash 88d9df1] Add 'l' to squash.txt
 1 file changed, 1 insertion(+)
[squash 7e8419c] Add 'l' to squash.txt
 1 file changed, 1 insertion(+)
[squash 6b6598f] Add 'o' to squash.txt
 1 file changed, 1 insertion(+)
[squash 50f66a3] Add ',' to squash.txt
 1 file changed, 1 insertion(+)
[squash a7977eb] Add ' ' to squash.txt
 1 file changed, 1 insertion(+)
[squash efa0f7c] Add 'w' to squash.txt
 1 file changed, 1 insertion(+)
[squash 67840e7] Add 'o' to squash.txt
 1 file changed, 1 insertion(+)
[squash f8ff386] Add 'r' to squash.txt
 1 file changed, 1 insertion(+)
[squash d0d728b] Add 'l' to squash.txt
 1 file changed, 1 insertion(+)
[squash 0f9e1f8] Add 'd' to squash.txt
 1 file changed, 1 insertion(+)
```

3. git rebase -i master
```
pick e87e4aa Add 'H' to squash.txt
pick 008b474 Add 'e' to squash.txt
pick 88d9df1 Add 'l' to squash.txt
pick 7e8419c Add 'l' to squash.txt
pick 6b6598f Add 'o' to squash.txt
pick 50f66a3 Add ',' to squash.txt
pick a7977eb Add ' ' to squash.txt
pick efa0f7c Add 'w' to squash.txt
pick 67840e7 Add 'o' to squash.txt
pick f8ff386 Add 'r' to squash.txt
pick d0d728b Add 'l' to squash.txt
pick 0f9e1f8 Add 'd' to squash.txt
```

4. only keep 1 pick, the remaining are squash
```
pick e87e4aa Add 'H' to squash.txt
squash 008b474 Add 'e' to squash.txt
squash 88d9df1 Add 'l' to squash.txt
squash 7e8419c Add 'l' to squash.txt
squash 6b6598f Add 'o' to squash.txt
squash 50f66a3 Add ',' to squash.txt
squash a7977eb Add ' ' to squash.txt
squash efa0f7c Add 'w' to squash.txt
squash 67840e7 Add 'o' to squash.txt
squash f8ff386 Add 'r' to squash.txt
squash d0d728b Add 'l' to squash.txt
squash 0f9e1f8 Add 'd' to squash.txt
```

5. git commit window will become this
```
# This is a combination of 12 commits.
# This is the 1st commit message:

Add 'H' to squash.txt

# This is the commit message #2:

Add 'e' to squash.txt

# This is the commit message #3:

Add 'l' to squash.txt

# This is the commit message #4:

Add 'l' to squash.txt

# This is the commit message #5:

Add 'o' to squash.txt

# This is the commit message #6:

Add ',' to squash.txt

# This is the commit message #7:

Add ' ' to squash.txt

# This is the commit message #8:

Add 'w' to squash.txt

# This is the commit message #9:

Add 'o' to squash.txt

# This is the commit message #10:

Add 'r' to squash.txt

# This is the commit message #11:

Add 'l' to squash.txt

# This is the commit message #12:

Add 'd' to squash.txt

"/tmp/rebase-sandbox/.git/COMMIT_EDITMSG" 64L, 1222C
```

6. modify commit window with a better message
```
add squash.txt with contents "Hello, world"

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Wed Feb 17 01:50:10 2021 -0500
#
# interactive rebase in progress; onto a09e57e
# Last commands done (12 commands done):
#    squash d0d728b Add 'l' to squash.txt
#    squash 0f9e1f8 Add 'd' to squash.txt
# No commands remaining.
# You are currently rebasing branch 'squash' on 'a09e57e'.
#
# Changes to be committed:
#       new file:   squash.txt
#
```

7. success
```
$git log --oneline
a2709f1 (HEAD -> squash) add squash.txt with contents "Hello, world"
a09e57e (master) add farewell.txt
97cf6a7 change greeting.txt to hello Linux
e8fa4d3 initial commit
$
```

8. checkout to master branch and rebase
```
$git checkout master 
$git rebase squash
First, rewinding head to replay your work on top of it...
Fast-forwarded master to squash.
$git log --oneline
a2709f1 (HEAD -> master, squash) add squash.txt with contents "Hello, world"
a09e57e add farewell.txt
97cf6a7 change greeting.txt to hello Linux
e8fa4d3 initial commit
```

9. delete squash branch
```
$git branch -D squash 
Deleted branch squash (was a2709f1).
$git branch -a
* master
```
