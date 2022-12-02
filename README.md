# Linux-Command-All-in-One-
<h6> Basic command start </h6>
date  // to display the current date <br>
who  // to provide details about currently loggined user <br>
whoami //to display the currently logined user name <br>
man //to provide manual<br>
clear // to clear commands from terminal<br>
pwd  // to show present working directory<br>
cal   cal 2028  cal 11 2023  // to display calendar<br>
uptime  //uptime of system<br> 
df  //show disk usage<br>
du  //show directory space usage<br>
free  //show memory and swap usage<br>
passwd / to set/reset password<br><br>
ls   ls -a   ls -l   ls -al   //to show content of files and directories<br>
cat>hello.txt //to create a text file<br>
cat hello.txt //to view content of file<br>
cat>hello.txt //to rewrite into a file<br>
cat>>hello.txt //to append the file<br>
cat file1.txt file2.txt > file3.txt   //to add content of two files to single<br>
ctrl +d //to save file content<br>
touch //to create empty file<br>
rm //to remove file or directory<br>
cd     cd ..    //to change directory<br>
grep pattern filename   //to search for a pattern in a file it's give a whole line <br>
gedit   //to edit the file graphically<br>
mkdir  //to create a directory<br>
rmdir  //to del empty dir<br>
rm -rf dirname  //to del dir w/c is not empty<br>
cp     //cp source  destination      to copy a file<br>
mv    //to move the file from one location to another<br>
ps // currently working process<br>
top // all running process<br>
useradd    adduser    //to add new user<br>
userdel      // to del user<br>
redhat-config-network      //to open network configuration manager<br>
ifconfig  //to check network details<br>
ping id address<br>
service network restart<br>
more filename // view the content of the text file,<br>
head filename  //first 10 lines<br>
tail filename  //last 10 lines<br>

<h6>Basic Command end Here </h6><br>

#
<h6>Add a New Group</h6><br>

groupadd name_of_the group<br>
# Add an Existing User Account to a Group<br>
usermod -a -G examplegroup exampleusername<br>
# Change a User’s Primary Group<br>
usermod -g new_group_name user_name<br>
# View the Groups a User Account is Assigned To groups<br>
# To view the numerical IDs associated with each group, run the id  command instead:<br>
id <br>
# Create a New User and Assign a Group in One Command<br>
useradd -G examplegroup exampleusername<br>
=> You’ll want to assign a password for that user afterwards, of course:<br>
passwd exampleusername<br>
# Add a User to Multiple Groups<br>
usermod -a -G group1,group2,group3 user_name<br>
# View All Groups on the System<br>
getent group<br>

<h6>Add a New User</h6><br>
<p>
When we run ‘useradd‘ command in Linux terminal, it performs following major things:
1.It edits /etc/passwd, /etc/shadow, /etc/group and /etc/gshadow files for the newly created User account.
2.Creates and populate a home directory for the new user.
3.Sets permissions and ownerships to home directory.
</p>

# Add a User<br>
useradd username<br>

# How to give a password to the user<br>
passwd username<br>
<p> Once a new user created, it’s entry automatically added to the ‘/etc/passwd‘ file. The file is used to store users information and the entry should be.</p>
The above entry contains a set of seven colon-separated fields, each field has it’s own meaning. Let’s see what are these fields:
1.Username: User login name used to login into system. It should be between 1 to 32 charcters long.
2.Password: User password (or x character) stored in /etc/shadow file in encrypted format.
3.User ID (UID): Every user must have a User ID (UID) User Identification Number. By default UID 0 is reserved for root user and UID’s ranging from 1-99 are reserved for other predefined accounts. Further UID’s ranging from 100-999 are reserved for system accounts and groups.
4.Group ID (GID): The primary Group ID (GID) Group Identification Number stored in /etc/group file.
5.User Info: This field is optional and allow you to define extra information about the user. For example, user full name. This field is filled by ‘finger’ command.
6.Home Directory: The absolute location of user’s home directory.
7.Shell: The absolute location of a user’s shell i.e. /bin/bash.

# . Create a User with Different Home Directory<br>
useradd -d /home/user1 arun<br>

# You can see the user home directory and other user related information like user id, group id, shell and comments.<br>
cat etc/passwd | grep user1<br><br>

# Create a User with Specific User ID<br>
 whenever we create a new user accounts in Linux, it assigns userid 500, 501, 502 and so on…<br>
 useradd -u 952 username<br>
 
# Create a User with Specific Group ID<br>
useradd -u 952 -g 152 username<br>

# Add a User to Multiple Groups<br>
useradd -G admins,webadmins,developers username<br>
Next, verify that the multiple groups assigned to the user with id command.
id username<br>

# Add a User without Home Directory<br>
useradd -M username<br>
Now, let’s verify that the user is created without home directory, using ls command.
nothing exist inide the home directory

# Create a User with Password Expiry Date<br>
 useradd  2023-03-14 -e user_name<br>
 
 <h6> Cat and Mount Command </h6><br>

# cat command ussing for different purpose.<br>
cat > fileName	To create a file.<br>
cat oldfile > [newfile]	To copy content from older to new file.<br>
cat file1 file2 and so on > new file name	To concatenate contents of multiple files into one.<br>
cat -n/cat -b fileName	To display line numbers.<br>
cat -e fileName	To display $ character at the end of each line.<br>

# The mount command attaches the filesystem of an external device to the filesystem of a system.<br>
fdisk -l // to check the sdb/filename<br>
now mkdir inside mnt or media using command <br>
mkdir /mnt/usb-drive<br>
mount /sdb/filename /mnt/usb-drive<br>

<h6> Linux Chown Command Examples to Change Owner and Group </h6><br>
The concept of owner and groups for files is fundamental to Linux. Every file is associated with an owner and a group. You can use chown and chgrp commands to change the owner or the group of a particular file or directory.<br>

firstly check the file owner  by using<br>
ls -l filename<br>
then ,<br>
chown new_user_name filename<br>

# Change the group of a file<br>
chown :user1 filename<br>

#change the owner and group of a file<br>
chown newowner:newgroup filename<br>

Note When the chown command was issued on symbolic link to change the owner as well as the group then its the referent of the symbolic link ie ‘tmpfile’ whose owner and group got changed. This is the default behavior of the chown command. Also, there exists a flag ‘–dereference’ for the same.<br>
# chown ownwename:groupname sym_file<br>

<h6>How to change a root password </h6><br>
step1 => double click then click e then go on kernal click enter then  space 1 then click b run commad passwd done<br>

<h6>Display Hard links </h6><br>
ln myfile linkname<br>
check inode number should be same using command ls -li <br>
=> hard-links cannot point to directories<br>

<h6>Display Soft Links </h6><br>
ln -s mufile softfile<br>
check ls -li check link count is increase by  2<br>

<h6>Runlevel</h6><br>
1. Change the behivour of the os<br>
2. runlevel 0 shoutdown<br>
3. runlevel 1 single user for root<br>
4. runlevel 2 multiple user no network<br>
5. runlevel 3 use for server side network but no gui<br>
6. runlevel 4 reserved for scientific purpose<br>
7. rulevel 5 workstation and normal PC<br>
8. runlevel 6 reboot<br>

<h6> file and directory permission </h6>
1. 4 read<br>
2. 2 write<br>
3. 1 execute<br>

chmod 777 filename //Numerical notation<br>
1. for owner<br>
2. for group<br>
3. for others<br>

chmod u+rwx,g+r,o+w filename // Symbolic notation<br>
chmod u=rw,g=rwz,o=r filename //override previous notation<br>

<h6>find command </h6><br>
The find command helps us to find a particular file within a directory.<br>
find . -name "*.txt" <br>

<h6>grep command </h6><br>
The 'grep' command stands for "global regular expression print". grep command filters the content of a file which makes our search easy.
grep <searchWord> <file name>  <br>

 <h6> locatecommand </h6><br>
The locate command and find command is used to search a file by name. But, the difference between both commands is that locate command is a background process and searches the file in the database whereas, find command searches in the filesystem. The locate command is much faster than find command.<br>

 locate <file name><br>
 
 <h6> vim editor </h6><br>
 
 vim has three modes<br>
 1. command<br>
 2. Input<br>
 3. Last Line<br>
 
 vi editor can be used as a gui mode as well as cui mode.<br>
 
<h6> Tee command </h6><br>
 
The tee command, used with a pipe, reads standard input, then writes the output of a program to standard output and simultaneously copies it into the specified file or files. Use the tee command to view your output immediately and at the same time, store it for future use.<br>
 
tee -a filename //for append<br>
-h // user readable form<br>
tee --help // to show all options<br>

 <h6> Some process command </h6><br><br>
 Simplest way to start a background process is to add an ampersand(&) at end of the command.<br>
 kill => command use to kill the process<br>
 ps -f => give more details about the process<br>
 top => display top process.<br>
 free => display information about free & used memory on the system.<br>
 df => report filesystem disk space usage<br>
 
 <h6> Tar command (still some command left)</h6><br>
 
 It's used to compressed or decompressed file<br>
 -c compress<br>
 -v verbose<br>
 -f filename<br>
 -x extract<br>
 
 tar -cvf Archieve_test.tar /home/utilizers<br>
 
 
 <h6> Word Count </h6><br>
 wc file 2<br>
 4 6 29 file2<br>
 4 no. of lines<br>
 6 no. of words<br>
 29 no. of char<br>
 
 <h6>Umask command </h6><br>
 The umask command in Linux is used to set default permissions for files or directories the user creates.<br>
 The umask command specifies the permissions that the user does not want to be given out to the newly created file or directory.<br>
 umask works by doing a Bitwise AND with the bitwise complement(where the bits are inverted, i.e. 1 becomes 0 and 0 becomes 1) of the umask.<br>
 The bits which are set in the umask value, refer to the permissions, which are not assigned by default,<br>
 as these values are subtracted from the maximum permission for files/directories.<br>
 Here, the first digit, 0 is called the sticky bit, it is a special security feature.The next three digits represent the octal values of the umask for a file or  <br>
 directory .(1st digit for user 2nd digit for group 3rd digit for other) (Now, for eg i give umask 0005 that's means for user give i give 0 and for other <br>
 give 0 and for other i give 5 (futher convert into decimal 101 that's means 1 for read 0 for write 1 for execute).<br>
 
 <h6>alias command in Linux with Examples</h6>
 Alias is like a shortcut command which will have same functionality as if we are writing the whole command.<br>
 alias name="command" <br>
 unalias [alias name] <br>
 -p option : This option prints all the defined aliases is reusable format.<br> 
Syntax: <br>
alias -p <br>

 <h6> diff command in Linux with examples </h6> <br> 
 
 diff stands for difference. This command is used to display the differences in the files by comparing the files line by line.<br>
 Unlike its fellow members, cmp and comm, it tells us which lines in one file have is to be changed to make the two files identical.<br> 
 Special symbols are: <br>
 a : add <br>
 c : change <br>
 d : delete <br>
 
 <h4> Scripting </h4> <br>
 // Create a scripting file with .sh extension <br>
 // write a code <br>
 // chmod u+x filename <br>
 // ./filename.sh <br>
 Some Useful Symbol <br>
 “   : double quote <br>
 `   : back quote <br>
Echo command is well appreciated when trying to debug scripts. <br>
Syntax :  echo {options}  string <br>
Options: -e : expand \ (back-slash ) special characters <br>
		       -n : do not output a new-line at the end. <br>

echo "Please enter three filenames:” <br>
read  filea fileb filec  <br>
 
Programming features of the UNIX/LINUX shell<br>
Shell variables:  Your scripts often need to keep values in memory for later use.  Shell variables are symbolic names that can access values stored in memory<br>
Operators:  Shell scripts support many operators, including those for performing mathematical operations<br>
Logic structures:  Shell scripts support sequential logic (for performing a series of commands), decision logic (for branching from one point in a <br>
script to another), < looping logic (for repeating a command several times), and case logic (for choosing an action from several possible alternatives) <br>

 //Variable <br>
 
Variables are symbolic names that represent values stored in memory <br>
Three different types of variables <br>
Global Variables: Environment and configuration variables, capitalized, such as HOME, PATH, SHELL, USERNAME, and PWD. <br>
When you login, there will be a large number of global System variables that are already defined. These can be freely referenced and used in your shell scripts.<br> 
Local Variables<br>
Within a shell script, you can create as many new variables as needed. Any variable created in this manner remains in existence only within that shell.<br>
Special Variables<br>
Reversed for OS, shell programming, etc. such as positional parameters $0, $1 … <br>

 
// Create array and list <br>
To create lists (array) – round bracket <br>
	$ set Y = (UNL 123 CS251) <br>
To set a list element – square bracket <br>
	$ set Y[2] = HUSKER <br>
To view a list element:<br>
	$ echo $Y[2] <br>
Example: <br>
			#!/bin/sh <br>
			a=(1 2 3) <br>
			echo ${a[*]} <br>
			echo ${a[0]} <br>
	Results:	1 2 3 <br>
			1 <br>
 
 // Positional Parameter <br>
When a shell script is invoked with a set of command line parameters each of these parameters are copied into special variables.<br>
 that can be accessed <br>
$0 This variable that contains the name of the script <br>
$1, $2, ….. $n 1st, 2nd 3rd command line parameter<br>
$#  Number of command line parameters<br>
$$  process ID of the shell<br>
$@ same as $* but as a list one at a time (see for loops later )<br>
 $?  Return code ‘exit code’ of the last command<br>
Shift command: This shell command shifts the positional parameters by one towards the beginning and drops $1 from the list. After a shift $2 becomes $1 , and so on … It is a useful command for processing the input parameters one at a time.<br>

Example: 
    Invoke :  ./myscript  one two buckle my shoe<br>
    During the execution of myscript variables $1 $2 $3 $4 and $5 will contain the values one, two, buckle, my, shoe   respectively.<br>

 // Shell operator <br>
  A shell variable take on the generalized form variable=value (except in the C shell).<br>
		$ set x=37; echo $x <br>
		37 <br>
		$ unset x; echo $x <br>
		x: Undefined variable.<br>
  You can set a pathname or a command to a variable or substitute to set the variable.<br>
		$ set mydir=`pwd`; echo $mydir<br>
 
 // Arithemetic Operator <br>
 vi math.sh <br>
		#!/bin/sh<br>
		count=5<br>
		count=`expr $count + 1 `<br>
	echo $count<br>
chmod u+x math.sh<br>
math.sh<br>

 
 // Apache is the most commonly used Web server on Linux systems <br>
 
// FTP (stands for “File Transfer Protocol”) is a standard and old network protocol<br>
// used for the transfer of files between a client and server on a computer network.<br>

// A Samba file server enables file sharing across different operating systems over a network.<br>
// It lets you access your desktop files from a laptop and share files with Windows and macOS users.<br>
// This guide covers the installation and configuration of Samba on Ubuntu.<br>
// Samba-client for cli and samba-swat for gui are used  <br>

What is an advantage of SMB over FTP?<br>
What is an advantage of SMB over FTP? ​ Only with SMB can data transfers occur in both directions.<br>
Only SMB establishes two simultaneous connections with the client, making the data transfer faster.​<br> 
SMB is more reliable than FTP because SMB uses TCP and FTP uses UDP.<br>

// Network File System (NFS) NFS allows a system to share directories and files with others over a network. <br>
// By using NFS, users and programs can access files on remote systems almost as if they were local files.<br>

 
 



 
 








 



