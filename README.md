# final
final for goldstein 


What is the difference between  sudo apt-get update and sudo apt-get upgrade ?
    - sudo apt-get update will update the package indices WHILE sudo apt-get upgrade will update all installed        packages on your system.


We can use the up arrow to page through, and Control-R to search, the history of commands we have previously typed.  Where does the system store the commands that you previously typed?

    The system will store the commands in /var since the history is only a temporary file. 

_______________________________________________________________________________________________________________
Explain the steps that you would need to take to permanently add a new partition to a system.  Be sure to note specific commands that you would use as well as any files that you would edit.

Answer : To add a new partition to the system:

 Use parted to create a new partition.

Make file system: mkfs.ext4   or  mkfs.btrfs

Clean the file system: e2fsck

Resize it:    resize2fs or btrfs filesystem resize

Get the PARTUUID with blkid

Edit /etc/fstab

Issue mount -a  to make sure that the partition mounts; rebooting without doing this might prevent the system from starting up.



_______________________________________________________________________________________________________________

Describe what the following command does:    tar -tvf lab7.tar

Answer : Display a detailed (-v) list (-t) of the contents of the lab7.tar file (-f)
         It lists the archive (tar) file. It does not archive the file.

_______________________________________________________________________________________________________________
In Linux, everything is treated as a file.  In what directory would you find the "files" for the standard input and the standard output devices?

    Answer: /dev

_______________________________________________________________________________________________________________

Describe what the following command does:     grep -vi "The[^m]" /usr/share/common-licenses/GPL-3

Answer : Prints everything other than lines that contain  The[^m] (“the” followed by anything other than an m) while ignoring case.

_______________________________________________________________________________________________________________
Explain why a system would have several partitions.  Be specific.


Answer To protect against storage space filling up and protects critical functions (such as the OS).  logs, home directories are typically put into their own partition

It has nothing to do with the security of  the data. 

_______________________________________________________________________________________________________________
A software sales rep says that they have a limited time special (a 42% discount) on a 100-user Linux server license.  What would your response be to the sales rep?

Answer: Scam! Linux is a free distribution. 

_______________________________________________________________________________________________________________
Assume that you are logged in as the user csis400  and are in your home directory. From the Bash $ prompt, what single line would you enter to edit the file /etc/sendipaddr ?

Answer: sudo nano /etc/sendipaddr

_______________________________________________________________________________________________________________
What would the BASH command line

export PS1="[\t \d \u@\h \W]"     change?  Describe what will be displayed after the change.

Answer: The prompt changes from $ to time date user@hostname PWD in brackets. For example:

[11:56:38 Sun Oct 3 igoldstein@olsen lab2]

CHANGES THE PROMPT
_______________________________________________________________________________________________________________

Assume that you are logged in as the user csis400 and are in your home directory.  You have a file called welcome.sh in your home directory, and the permissions have been set to allow execution.  However, when you type in the filename to run it, you get a “command not found” error.  Explain why this is happening, then explain two different ways that you can  get the file to run.


It is not in the PATH environment variable.

You could:

Preface it with ./
Add the home directory to your path
Copy the file to a directory in the path

______________________________________________________________________________________________________________
I wanted to write a shell script that prompts a user for their name and two numbers, and then displays the sum and the difference of the two numbers.  I was in a rush, and did not have time to debug my first attempt at writing this script.  Following the process that you have used in lab, clone http://github.com/ProfGoldstein/linuxmidterm.git and look at the file sumdiff.sh    Then, debug the script and paste the contents of the corrected file.

Desired sample interaction (input in **bold**):

What is your name? **Ira**


Hello Ira. We are going to calculate the sum and difference of two numbers.

 

What is your first number? **42**

What is your second number? **24**

 

42 + 24 = 66

42 - 24 = 18

###############################################ANSWER########################################################

#!bin/bash         changes to     #!/bin/bash        
# Using echo, clear the screen and prompt the user for their name  Add -e to enable backslash commands

echo -n -e '\fWhat is your name? '

read NAME

# Great the user by name   Add the $ to NAME    

echo

echo "Hello $NAME. We are going to calculate the sum and difference of two numbers."

echo


# Perform calculations   Remove the $ from the start of the line and fix parens    and add $ on SUM         2

$SUM=(FIRSTNUMBER+SECONDNUMBER)    becomes  SUM=$((FIRSTNUMBER+SECONDNUMBER))

$DIFFERENCE=$((FIRSTNUMBER-SECONDNUMBER))   becomes   DIFFERENCE=$((FIRSTNUMBER-SECONDNUMBER))

 

# Display Results  Change the single ' to double "

echo

echo "$FIRSTNUMBER + $SECONDNUMBER = $SUM"

echo "$FIRSTNUMBER - $SECONDNUMBER = $DIFFERENCE"


______________________________________________________________________________________________________________


Compare and contrast Unix, Linux, and GNU. Be specific for all three.


Unix is the first of the three, created in 1969 by Bell Labs it was created to solve compatibility issues that had not been solved at the time. Programs not being multi-system, not being able to work with one another, etc... Therefore they created Unix to be simple and written in C rather than assembly language. Linux is then created in response as a free version of UNIX which was compliant with UNIX itself. Linux uses alot from GNU (Gnu is not Linux), which is yet another free version of UNIX. GNU's was written only looking at the manual for Unix, making them equal in power, yet GNU was free. Due to GNU's rise in popularity, Linux uses GNU software such as its Bash. 


from goldstein .....

While I expect more detail, basically:

Unix:   Commercial Software developed at Bell Labs (AT&T)

GNU:  Open source versions of Unix utilities

Linux: Open source version of the Unix kernel

______________________________________________________________________________________________________________


Who is Richard Stallman?

Richard Stallman is the creator of GNU. Believes in open source. 


______________________________________________________________________________________________________________




