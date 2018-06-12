# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > pwd
cd
..
touch file.txt
-rm
mv
ls -a
cp
git commit -m "commit message here"
git status

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  lists
`ls -a`  lists all + hidden files
`ls -l`  lists with long formats (permissions)
`ls -lh`  lists with long formats with readable size
`ls -lah`  lists all with readable sizes
`ls -t`  sorts by time and date
`ls -Glp`  

> > lists
lists all hidden files too
lists with long formats
lists with long formats with readable size
lists all (hidden) with readable sizes
sorts by time and date
lists everything

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > -R
-u
-a
-p
-d

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > displays all files as rows across the screen in reverse order in long format listing excluding owner name and their size
and an example would be ls -xargs to list all the files in your working directory in reverse order
 

