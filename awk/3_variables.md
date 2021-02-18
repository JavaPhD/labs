# variables
- $0: whole line
- $1: first column
- $2: second column
..
- $n: nth column

```
$awk -F: '{print $1}' /etc/passwd | head
root
bin
daemon
adm
lp
sync
shutdown
halt
mail
operator
$
```
