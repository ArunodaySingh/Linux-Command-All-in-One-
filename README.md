# Linux-Command-All-in-One-
<h6> Basic command start </h6>
date  // to display the current date \n
who  // to provide details about currently loggined user
whoami //to display the currently logined user name
man //to provide manual
clear // to clear commands from terminal
pwd  // to show present working directory
cal   cal 2028  cal 11 2023  // to display calendar
uptime  //uptime of system
df  //show disk usage
du  //show directory space usage
free  //show memory and swap usage
passwd / to set/reset password
ls   ls -a   ls -l   ls -al   //to show content of files and directories
cat>hello.txt //to create a text file
cat hello.txt //to view content of file
cat>hello.txt //to rewrite into a file
cat>>hello.txt //to append the file
cat file1.txt file2.txt > file3.txt   //to add content of two files to single
ctrl +d //to save file content
touch //to create empty file
rm //to remove file or directory
cd     cd ..    //to change directory
grep pattern filename   //to search for a pattern in a file it's give a 
gedit   //to edit the file graphically
mkdir  //to create a directory
rmdir  //to del empty dir
rm -rf dirname  //to del dir w/c is not empty
cp     //cp source  destination      to copy a file
mv    //to move the file from one location to another
ps // currently working process
top // all running process
useradd    adduser    //to add new user
userdel      // to del user
redhat-config-network      //to open network configuration manager
ifconfig  //to check network details
ping id address
service network restart
more filename // view the content of the text file,
head filename  //first 10 lines
tail filename  //last 10 lines

<h6>Basic Command end Here </h6>

#
<h6>Add a New Group</h6>

groupadd name_of_the group
# Add an Existing User Account to a Group
usermod -a -G examplegroup exampleusername
# Change a User’s Primary Group
usermod -g new_group_name user_name
# View the Groups a User Account is Assigned To
groups
# To view the numerical IDs associated with each group, run the id  command instead:
id
# Create a New User and Assign a Group in One Command
useradd -G examplegroup exampleusername
=> You’ll want to assign a password for that user afterwards, of course:
passwd exampleusername
# Add a User to Multiple Groups
usermod -a -G group1,group2,group3 user_name
# View All Groups on the System
getent group

<h6>Add a New User</h6>
<p>
When we run ‘useradd‘ command in Linux terminal, it performs following major things:
1.It edits /etc/passwd, /etc/shadow, /etc/group and /etc/gshadow files for the newly created User account.
2.Creates and populate a home directory for the new user.
3.Sets permissions and ownerships to home directory.
</p>

# Add a User
useradd username

# How to give a password to the user
passwd username
<p> Once a new user created, it’s entry automatically added to the ‘/etc/passwd‘ file. The file is used to store users information and the entry should be.</p>
The above entry contains a set of seven colon-separated fields, each field has it’s own meaning. Let’s see what are these fields:
1.Username: User login name used to login into system. It should be between 1 to 32 charcters long.
2.Password: User password (or x character) stored in /etc/shadow file in encrypted format.
3.User ID (UID): Every user must have a User ID (UID) User Identification Number. By default UID 0 is reserved for root user and UID’s ranging from 1-99 are reserved for other predefined accounts. Further UID’s ranging from 100-999 are reserved for system accounts and groups.
4.Group ID (GID): The primary Group ID (GID) Group Identification Number stored in /etc/group file.
5.User Info: This field is optional and allow you to define extra information about the user. For example, user full name. This field is filled by ‘finger’ command.
6.Home Directory: The absolute location of user’s home directory.
7.Shell: The absolute location of a user’s shell i.e. /bin/bash.

# . Create a User with Different Home Directory
useradd -d /home/user1 arun

# You can see the user home directory and other user related information like user id, group id, shell and comments.
cat etc/passwd | grep user1

# Create a User with Specific User ID
 whenever we create a new user accounts in Linux, it assigns userid 500, 501, 502 and so on…
 useradd -u 952 username
 
# Create a User with Specific Group ID
useradd -u 952 -g 152 username

# Add a User to Multiple Groups
useradd -G admins,webadmins,developers username
Next, verify that the multiple groups assigned to the user with id command.
id username

# Add a User without Home Directory
useradd -M username
Now, let’s verify that the user is created without home directory, using ls command.
nothing exist inide the home directory

# Create a User with Password Expiry Date
 useradd  2023-03-14 -e user_name
 
 <h6> Cat and Mount Command </h6>

# cat command ussing for different purpose.
cat > fileName	To create a file.
cat oldfile > [newfile]	To copy content from older to new file.
cat file1 file2 and so on > new file name	To concatenate contents of multiple files into one.
cat -n/cat -b fileName	To display line numbers.
cat -e fileName	To display $ character at the end of each line.

# The mount command attaches the filesystem of an external device to the filesystem of a system.
fdisk -l // to check the sdb/filename
now mkdir inside mnt or media using command 
mkdir /mnt/usb-drive
mount /sdb/filename /mnt/usb-drive

<h6> Linux Chown Command Examples to Change Owner and Group </h6>
The concept of owner and groups for files is fundamental to Linux. Every file is associated with an owner and a group. You can use chown and chgrp commands to change the owner or the group of a particular file or directory.

firstly check the file owner  by using
ls -l filename
then ,
chown new_user_name filename




 



