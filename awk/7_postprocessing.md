# similar to preprocessing, END will show once at the end
```
$cat !$
cat testfile
BEGIN{
print "start reading..."
print "user id \t home directory"
print "________ \t _________"
}
{
print $1 " \t " $6
}
END{
print "finished reading"
}
```
```
$awk -F: -f testfile /etc/passwd | head
start reading...
user id 	 home directory
________ 	 _________
root 	 /root
bin 	 /bin
daemon 	 /sbin
adm 	 /var/adm
lp 	 /var/spool/lpd
sync 	 /sbin
shutdown 	 /sbin
$
```
