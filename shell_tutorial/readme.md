# Shell tutorial

## different shell commands

- `date`  will tell you present time
- `echo` is like print.

- How computer know about date

  - There are some place where this things are already determined. We can also use
    for loop and other programmic things through those. Later those will be described in detail.

### Environment Variable

- PATH -> colon separated list
  - Whenever a program will run it will look each of the folder in PATH variable and see 
    all the folders contains echo and run it

- `pwd` -> present working directory
- `which echo` -> wil tell where the echo file is. 
- `cd -` ->cd(dash) will go to previous directory you were.

### Arguments 

- `ls --help` will go to help for `ls` command
- `ls -l` more informaiton about the files
- `mv source destination` -> move or rename
- `cp source destination` -> copy
- `rm` -> remove a file use `r` flag to remove directory
- `rmdir` -> remove directory if it is only empty
- `mkdir`-> create a new directory

   1. `mkdir my photo` -> create two directory one name my and another name directory
   2. `mkdir "my photo"`  -> create one directory named as my photo.

- `man` takes an argument name of one program (like ls) and give the manual of the ls

   1. `man ls` will give the manual of ls program will give the manual of ls program.

- `cntrl + l` will clear the screen and go back at the top of the screen

## Chaining or piping

- `echo hello > hello.txt` -> means the output of the `echo hello` will go to a file named as hello.txt file, in current directory.

- `cat` will print the content of the file.

   1. `cat hello.txt` will print the content of hello.txt file.
   2. `cat < hello.txt` open hello.txt and output will be used an argument name for cat and it will print
   the hello.txt file content.
   3. Both can be done simultaneously. Somehow may be we don't want to use `cp` command. What we can do is `cat < hello.txt > hello2.txt`, what it is doing is cat take argument of `hello.txt` file and writing it to hello2.txt file.
   4. `>>` will append instead of overwriting the file.

- pipe(`|`) character. Take the output of the left program and use them 

  1. Normally `ls -l`  will print the directory content. `tail -n1` normally print last 1 line. 
  2. `ls -l| tail -n1` will print the last file of the current directory.
  3. `ls -l| tail -n1 > hello.txt` will save it to hello.txt file.

## Notion of a root user

- `sudo` super user do. where some thing needs super user permissions, sudo needs to be used.
- cd `/sys` -> this is whole new world, these are not file system of computer but kernel parameters, which looks like a file system.
- cd `/sys/backlight` will be the back light of your computer. and `cat brightness` brightness of the screen. One can actually change the brightness of the screen.
- Here if you want change something, then permission will be denied. If you use sudo still permissions will be denied.
- One can switch to root terminal by using `sudo su` the prompt will be changed from dollar to hash sign
- One convenient way actually use `echo 1060 | sudo tee brightness`. print 1060 and put it to brightness.
  
  1. `tee` if you want to move a logfile to another file but you also want to see it, then use `tee`. So it will forward to another file but use also standard output.
- With the tee command I don't need to go root user. And simply can be done as a sudo user. Not su required anymore.

## Opening a file

- `xdg-open filename` open a file.
