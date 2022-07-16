# LFCS

This Repository prepares you for LFCS Certification exam and give you basic understanding of Linux.

- Login into Local and Remote Graphically and via Text mode consoles
We can Log in from text-mode console which is known as terminal and via GUI.

- What is locally?
Local is the tech word which is in front of you or something you can physically access.
Computer on your desk in local

- What is Remote?
A server running somewhere else, like a server running on gcp, aws , azure etc is 

interacting with man, apropros, mandb

1. man - an interface to the on-line reference manuals

we can type 'man man' to see the options for man.

2. apropos - search the manual page names and descriptions

example:  apropos ls, apropos hostname,

3. If the apropos command does not work because our manual pages are not indexed, command to use to manually refresh these is :

'sudo mandb'
mandb command is used If the apropos command does not work, because your manual pages are not indexed.

We are trying to run apropos ssh command to get some details about the commands related to ssh but we are getting this error:

'ssh: nothing appropriate.'

The solution is to run sudo mandb to index our manual pages.