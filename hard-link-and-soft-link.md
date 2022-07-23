---------------------------------------------------------

Hard Links

---------------------------------------------------------


File system like ext4, xfs keeps track of data with the help of inode, as your file have blocks of data scattered all over the disk.

The inode remembers where all the pieces are stored. It also keeps track of metadata, things like permissions, when the data was last modified or last accessed and so on.

The file points to inode 
inode points to all the block of data that we require.

``` sanketbisne@C02FN48BQ6LR LFCS % stat hard-link-and-soft-link.md 
16777233 13595557 -rw-r--r-- 1 sanketbisne staff 0 0 "Jul 23 20:14:42 2022" "Jul 23 20:14:42 2022" "Jul 23 20:14:42 2022" "Jul 23 20:14:42 2022" 4096 0 0 hard-link-and-soft-link.md ```

Inode= 16777233

Link=1

Why hard link?

To create a Backup of a file
To utilize the space of file, instead of creating a copy of file which points to different inode number, 
when we create a hard link of a file, it points to same inode number which doesn't waste the space.


- ` ln < path to target file > < path to link file> `

- example - ` ln hard-link-and-soft-link.md /Users/sanketbisne/Documents/LFCS/hardlink/sanket-hardlink.md `

Output after creating a hard link 

Target file - ``` 16777233 13595557 -rw-r--r-- 2 sanketbisne staff 0 1119 "Jul 23 20:39:41 2022" "Jul 23 20:39:41 2022" "Jul 23 20:39:41 2022" "Jul 23 20:14:42 2022" 4096 8 0 hard-link-and-soft-link.md ```

Link file - ``` 16777233 13595557 -rw-r--r-- 2 sanketbisne staff 0 1376 "Jul 23 20:41:00 2022" "Jul 23 20:41:00 2022" "Jul 23 20:41:00 2022" "Jul 23 20:14:42 2022" 4096 8 0 sanket-hardlink.md ```

As we can see now 
Inode number matches from both the files.
Link=2 , it means the hard link value is 2

Note : If all the Hard links are been removed, all the data itself will be erased.


Limitations
- We can only hard link to files and not to directories.
- we can also only hard link to files on the same file system.
- Not supported on different file systems.



---------------------------------------------------------

Soft Links

---------------------------------------------------------


Soft links are to manage the shortcuts.

Syntax - ln -s < path to target file > < path to link file >

example -  ln -s softlink1 /Users/sanketbisne/Desktop/softlink1.txt

s acts as a symolic link.

Hard link points to a inode but soft links points to a file -> path

- mkdir new
- echo "hi" >> hi.txt
- ln -s hi.txt ../LFCS/new/sanket-softlink.txt
- cd new
- ls -l

You will see the output as our new file created will point to its original file.

```

lrwxr-xr-x  1 sanketbisne  staff  6 23 Jul 22:59 sanket-softlink.txt -> hi.txt

```

Note:

We can soft link to files or directories on a different file system which differs from the way that linux handles hard links.



