# more variables
- ARGC     Retrieves the number of passed parameters.
- ARGV     Retrieves the command line parameters.
- ENVIRON     Array of the shell environment variables and corresponding values.
- FILENAME    The file name that is processed by awk.
- NF     Fields count of the line being processed.
- NR    Retrieves total count of processed records.
- FNR     The record which is processed.
- IGNORECASE     To ignore the character case.


# print variables
```
$awk '
> BEGIN{
> print ENVIRON["PATH"]
> }'
/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/sbin:/bin:/sbin:/var/lib/snapd/snap/bin:/home/tichen/.local/bin:/home/tichen/bin
$
```
