## git log

1.  basics:
```
$git log
commit 19bccdf6b65bfc9ad1721df18a63aacaf041b35a (HEAD -> master)
Author: gary chen <chen.tianqi@yahoo.com>
Date:   Tue Feb 16 22:04:39 2021 -0500

    modified greeting.txt

commit e8fa4d3581a7d1a983f91407d7ab506416f1629f
Author: gary chen <chen.tianqi@yahoo.com>
Date:   Tue Feb 16 21:35:24 2021 -0500

    initial commit
```
2. show in oneline  
```
$git log --oneline
19bccdf (HEAD -> master) modified greeting.txt
e8fa4d3 initial commit
```
3. show last 2 commits
```
$git log -n 2
commit 19bccdf6b65bfc9ad1721df18a63aacaf041b35a (HEAD -> master)
Author: gary chen <chen.tianqi@yahoo.com>
Date:   Tue Feb 16 22:04:39 2021 -0500

    modified greeting.txt

commit e8fa4d3581a7d1a983f91407d7ab506416f1629f
Author: gary chen <chen.tianqi@yahoo.com>
Date:   Tue Feb 16 21:35:24 2021 -0500

    initial commit
```
4. show details of one commit
```
$git show 19bccdf6b65bfc9ad1721df18a63aacaf041b35a
commit 19bccdf6b65bfc9ad1721df18a63aacaf041b35a (HEAD -> master)
Author: gary chen <chen.tianqi@yahoo.com>
Date:   Tue Feb 16 22:04:39 2021 -0500

    modified greeting.txt

diff --git a/greeting.txt b/greeting.txt
new file mode 100644
index 0000000..557db03
