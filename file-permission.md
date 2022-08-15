Every file has permission associated with it.

A root user can change the file permission of a file. Also a file can be added in a group.

To change a group of file.
chgrp < group name > < file directory>

ex : chgrp wheel <my_image.jpg>

groups 

-------------------------------------------------------------------------------------


To change user owner of File/Dir

`sudo chown jane family_dog.jpg`


To change user owner of file and group

`sudo chown aaron:family family_dog.jpg`

To see the permissions of a file

`ls -l`

-rw-r--r--@ 1 sanketbisne  staff  1206 16 Jul 15:50 introduction.md

- `-` means that it is a file
- `d` means it is a directory
- `c` means it is a character device
- `s` means it is a socket file
- `p` means it is a pipe.
- `b` means that is is a block device.

-rw-r--r--
1st 3 sections are for owner
2nd 3 sections are for group
3rd 3 sections are for others
rw- means that "owner" has permission to read and write the file but not to execute it.
r-- means that "group" has only read access to file.
r-- means that "others" has only read access to file.



Precedence
-------------------------------------------------------------------------------------

Permissions are evaluated from Left to Right

User->Group->Others

if suppose a person Ram is a part of group , ehich has rw permissions but ram has only read permission, then also ram is not able to perform the write operation because precedence is calculated from left to right.

To change file Permission of file

`chmod <code> file name`

`4-r 2-w 1-x`

`chmod <421-421-421> file name`

Example giving sanket.txt rwx permission on user , group and others
user   =   4+2+1 = 7
group  =   4+2+1 = 7
others =   4+2+1 = 7

`chmod 777 sanket.txt`

OR
user   =    u+  = u+w/u+rw/u+rwx
group  =    g+  = g+w/g+rw/g+rwx
others =    o+  = o+w/o+rw/o+rwx


file1 - `-rw-r--r--   1 sanketbisne  staff   521 15 Aug 12:16 basic-commands.md`

Now we will add our user sanketbisne -> execute permission on basic-commands.md

`chmod u+x basic-commands.md`

file1 updated - `-rwxr--r--   1 sanketbisne  staff   521 15 Aug 12:16 basic-commands.md`


lets remove the execute permission for our user

`chmod u-x basic-commands.md`

Output is as follows, it has removed execute permission on our user .

`-rw-r--r--   1 sanketbisne  staff   521 15 Aug 12:16 basic-commands.md`

Lets provide user -> read, write and execute permission , group -> read and execute permission and others -> read and write permission on the file.

`chmod u+rwx,g+rx,o+rw basic-commands.md`

Output is as follows.

`-rwxr-xrw-   1 sanketbisne  staff   521 15 Aug 12:16 basic-commands.md`

----------------------------------------------------------------------------------------------------------------

To remove permissions for our user , group and others

```
user   =    u-  = u-w/u-rw/u-rwx
group  =    g-  = g-w/g-rw/g-rwx
others =    o-  = o-w/o-rw/o-rwx
```
We can also use `stat < file name >` to see file permission.


