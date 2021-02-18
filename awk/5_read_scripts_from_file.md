# awk scripts in a file
```
$vi testfile
$cat !$
cat testfile
{print $1 " home is " $6}
$awk -F: -f testfile /etc/passwd | head
root home is /root
bin home is /bin
daemon home is /sbin
adm home is /var/adm
lp home is /var/spool/lpd
sync home is /sbin
shutdown home is /sbin
halt home is /sbin
mail home is /var/spool/mail
operator home is /root
$
```

# Awk script file can also use local defined variables
```
$cat testfile
{

text=$1 " home is " $6
print text

}
$awk -F: -f testfile /etc/passwd | head
root home is /root
bin home is /bin
daemon home is /sbin
adm home is /var/adm
lp home is /var/spool/lpd
sync home is /sbin
shutdown home is /sbin
halt home is /sbin
mail home is /var/spool/mail
operator home is /root
$
```
