# built-in variables
- FIELDWIDTHS     Specifies the field width.
- RS     Specifies the record separator.
- FS     Specifies the field separator, default is space.
- OFS  Specifies the Output separator, default is space.
- ORS  Specifies the Output separator.

# FS and OFS
```
$awk 'BEGIN{FS=":"; OFS="|---|"}{print $1,$3,$6}' /etc/passwd | head
root|---|0|---|/root
bin|---|1|---|/bin
daemon|---|2|---|/sbin
adm|---|3|---|/var/adm
lp|---|4|---|/var/spool/lpd
sync|---|5|---|/sbin
shutdown|---|6|---|/sbin
halt|---|7|---|/sbin
mail|---|8|---|/var/spool/mail
operator|---|11|---|/root
$
```

# FIELDWIDTHS
```
$cat !$
cat test
1.345-902
teryis handsome
$@@#$@#@---
$awk 'BEGIN{FIELDWIDTHS="3 4 3"}{print $1,$2,$3}' test
1.3 45-9 02
ter yis  han
$@@ #$@# @--
```

# FS and RS
```
$awk 'BEGIN{FS="\n"; RS=""}{print $1,$3}' test
jerry 222222
terry 333333
$cat test
jerry
blah blah
222222

terry
plah plah
333333
```
