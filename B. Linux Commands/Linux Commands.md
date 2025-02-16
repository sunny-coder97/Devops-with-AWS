## Basic Linux Commands

__whoami__: It gives us logged in user name

__date__ : display current date

__cal__ : display calendar

__clear__ : to erase terminal content

__pwd__ : To display present working directory

__mkdir__ : to create directory

__rmdir__ : to delete empty directory

 >To delete non-empty directories  we will use below command
        
* __$ rm -r dirname__ [For Recursively deleting the directories ]

__cd__ : to change directory 

__cd__ ~ [this command is used to reach at the user home directory]

__ls__ : To display files & directories of present working directory

* ls -l : display files and directories in alphabetical order
* ls -lr : reverse of alphabetical order
* ls -lt :  Display files based creation date & time (latest on top)
* ls -ltr : Display files based creation date & time (latest on bottom)

> __ls -lrt \*2024_bval_ny\*__ : This command is very useful when you want the search the files in a particular directory with this format .

__touch__ : To create empty files

* __$ touch f1.txt f2.txt f3.txt__

__cat__ :  create files with data , append data to existing file, display file content

* cat > filename   (To create file with content) [Ctrl + D to move out ]

* cat >> filename  (append data to existing file) [ >> this operator is generally used for appending the things] 

* cat filename (display file content)

* cat -n filename (To display the things with line numbers)

> cat command will display file data from top to bottom.

__tac__ : tac command will display file data from bottom to top

* __$ tac filename__

__cp__ : It is used to copy data from one file to another file/ copy file into some another directory

* __$ cp f1.txt f2.txt__

> To copy data from multiple files we need to use 'cat' command.
__$ cat f1.txt f2.txt > f3.txt__

__rm__ : to delete file

* __$ rm -f filename__ 

> __rm -f \*2023_07\*__ [ for removing all the files from a particular directory by giving the pattern]

__mv__ : to move / rename the file

*  __$ mv oldname  newname__ : [It is used for renaming the File]

* __$ mv filename location__ [It is used for moving the file to a particular location]

__wc__ : word count (It gives the lines , words and characters present in a particular file)

* __$ wc -l bval.txt__

__head__ : To display first 10 lines of file

* __$ head filename__ [Default first 10 lines , It will print]
* __$ head -12 filename__ [It will print first 12 lines]
* __$ head -50 filename__  [It will print first 50 lines]

__tail__ : To display last 10 lines of file

* __$ tail filename__  [Default last 10 lines, It will print]
* __$ tail  -15 filename__ (it will print last 15 lines)

> To check the latest logs of the application we will use the 'tail' command __$ tail -f filename__ (It will print the last 10 lines of the updated logs)

__sed__ : sed command is used for the below purposes .

* __sed__ stands for __Stream Editor__
* __sed__ is used for substitution/replacement OR we can delete the lines from the file as well without opening the file.
* We can replace one word with another word using __sed__ command without opening the file
   * __$ sed 's/aws/azure/' ashokit.txt__
> By default, SED command will not make changes in the original file. It will just print output on the terminal.

* $ __sed -i 's/aws/azure/' ashokit.txt__ [It will make changes and insert it into the file as well]

* __$ sed '$d' ashokit.txt__ [Delete last line of the file]

* __$ sed '5d' ashokit.txt__ [Delete 5th line of the file]

* __$sed '10,$d' ashokit.txt__ [Delete 10th line to the last line]

* __$sed '1,$d' ashokit.txt__ [Delete all the lines from the file]

__find and locate command:__

   * 'locate' and 'find' commands are used for file search

   * In every linux machine locate db will be available which stores linux file system details.

   * When we execute the locate command it will fetch details from locate db.

   * 'find' command will do search in entire linux file system

   * 'find' command is used for more advanced search

* __Search for the files under home directory with given name__

    * $ sudo find /home -name f1.txt

> If you are running __find /home -name f1.txt__ . It will execute without root user . It cannot search in all user’s directories .
    
* __Find empty files under /home__

     * $ sudo find /home -type f -empty

* __Find empty directories under /home__

   * $ sudo find /home -type d -empty

* __Find 30 days old files under /home directory__

   * $ sudo find /home -mtime 30 -print

* __Find & delete 30 days old files under /home directory__

    * $ sudo find /home -mtime 30 -delete




__man__ : It is like a helper command to know anything about the commands that we use in Linux .

__ping__ : To check connectivity

   * $ ping www.gmail.com
  * $ ping 13.12.109.21

__wget__ : To download files from internet using url

   * $ wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.10/bin/apache-tomcat-10.1.10-windows-x64.zip

__curl__ : It is used to send HTTP Request to URL

  * $ curl 192.168.1.123

__ifconfig__ : To get IP Address of  our machine

  * $ ifconfig

__free__ : To display memory details

__top__ : To display running processes

__htop__ : To display running processes in Graphical format

__history__ : It is used to display all commands executed (commands history)

__grep command__ :

* It stands for "Global Regular Expression Print" and it is a powerful utility in Linux used for searching and filtering text.

* The grep command searches for patterns or regular expressions in files or input streams and displays lines that match the specified pattern.

   *    __grep [options] pattern [file...]__

* Pattern matching print
   *  __$ grep "keyword" file.txt__

* Recursive print
     *    __$ grep -r "pattern" directory/__

* Ignore case
     * __$ grep -i "pattern" file.txt__

* print line numbers
     *   __$ grep -n "pattern" file.txt__

* Invert match (print files which are not matching given pattern)
     * __$ grep -v "pattern" file.txt__

__awk command__ :

* The awk command is a versatile text processing tool available in Unix-like operating systems, including Linux.
* It allows you to manipulate and extract data from structured text files, usually in a columnar format. 
* awk takes input, processes it line by line, and performs actions based on specified patterns and rules.

    * __awk 'pattern { action }' file__

    * $ cat > employee.txt 
        * Ashok manager account 45000 
        * John clerk account 25000 
        * Smith manager sales 50000 
        * Charles manager account 47000 
        * Ganesh peon sales 15000 
        * Mahesh clerk sales 23000 
        * Ram peon sales 13000 
        * Cathy director purchase 80000
    
    * __awk '{print}' employee.txt__
    * __awk '/manager/ {print}' employee.txt__ 
    * __awk '{print $1,$4}' employee.txt__ 
    * __awk '{print NR,$0}' employee.txt__ 
    * __awk '{print NR "- " $1 }' employee.txt__
    

__Q.__ How to check which linux version we are using ?

__Ans.__ $ cat /etc/os-release

__Q.__ How to check the Linux kernel details ?

__Ans.__ $ uname -r

__Q.__ What is the sudoers file ?

__Ans.__ Sudoers file is used to configure user permissions. __[visudo command]__

__Q__ What is a .bashrc file ?

__Ans.__ 

* For every user, .bashrc file will be created under the home directory. 
* .bashrc is a hidden file (it starts with .) & to display hidden files we will use __'ls -la'__ 
* Using .bashrc we can set Environment Variables for user accounts.



 

## Text Editor in Linux 


__vi__ command : Visual Editor

* Using 'vi' command we can work with text editor

* To open file we can use below command

     * __$ vi ashokit.txt__

* insert mode : __press 'i'__
* escape mode : __press 'esc'__

   * To save changes and close file => __esc + :wq__
   * To save changes and close file explicitly =>__esc+ :wq!__
   * Close file without saving changes => __esc + :q!__

> You can use all the shortcuts when you are in escape mode (__shift +g__ to reach end of the file)

## File Permissions in Linux & chmod command :

> In Linux , multiple users can access the linux machine at a time , then which user can access which file due to this reason we maintain the file permissions in Linux 

We have 3 types of permissions in Linux .
    
* __r__  : read
* __w__  : write
* __x__  : execute

> File Permission contains 3 sections (total 9 characters)

* User section (first 3 characters)
* Group Section (middle 3 characters)
* Others section (last 3 characters)

  * __-rwxrwxrwx f1.txt__  (It is a file and users, groups and others all have all the permissions)
  * __-rw-rw-r--  f2.txt__      (It is a file , users and groups have read-write permission and others have only read permission)
  * __-r--rw-rw- f3.txt__       (It is a file , users have read permission only , groups & others have read and write permission)
  * __dr-xr--rwx    linux__      (It is directory , user have read & execute permissions and group have only read permission and others have all the permissions)

> To change file permission we have __'chmod'__ command in Linux.

* \+  :  __means add permission__
* \-   : __means remove permission__

* __chmod u+x  f1.txt__ (adding execute permission for user)
* __chmod g+x  f2.txt__  (adding execute permission for group)
* __chmod o-x  f3.txt__  (removing execute permission for others)
* __chmod u+wx f4.txt__  (adding write and execute for user)

> File permissions we can manage with numeric numbers also

* 0 : No Permission
* 1 : Execute
* 2 : Write
* 3 : Execute + Write  [2+1]
* 4 : Read
* 5 : Read + Execute [4+1]
* 6 : Read + Write [4+2]
* 7 : Read + Write + Execute [4+2+1]

> __chmod 777 file.txt__ [this is the very command to provide the full access to a file.]

## Users and Group in Linux :

*  Linux is Multi User based OS
* We can create Multiple User accounts in one Linux Machine
* In Every Linux machine by default 'root' user account will be available

    * root user : __super user(su)__

* When we launched the EC2 instance ( Amazon Linux AMI ) We got an __'ec2-user'__ account also.

* For every user account one home directory will be available under __/home__ directory
        
    * __ec2-user__ : /home/ec2-user
    * __ashok__	 : /home/ashok
    * __john__	 :  /home/john
    * __cathy__	 : /home/cathy
    * __raju__ 	 : /home/raju

> We can get user account information by using __'id'__ command.


* __id username__  : It will tell us about the details of a particular user.

* __Switch to root user__:

   * __$ sudo su__ (switch to root account and it will point to that path from where this command was executed)
   * __$ sudo su -__ (switch to root user and point to root user home directory) /root 
   * __$ exit__  (exit from user account)

* __Working with users and group in Linux__ :

  * Switch to root user
    * __$ sudo su -__

  * Create New User account

    * __$ useradd uname__

  * Set Password for User

    * __$ passwd uname__

  * Display Users created

    * __$ cat /etc/passwd__

  * Switch to user account

    * __$ su username__

> By using the __'su'__ command we will switch to that user account but it will still point to the root user home directory but for pointing with the new user home directory we need to use __cd ~__ command .

* [__root__@ip-172-31-38-59 ~]# su john
* [__john__@ip-172-31-38-59 root]$ pwd
    * /root
* [__john__@ip-172-31-38-59 root]$ cd ~
* [__john__@ip-172-31-38-59 ~]$ pwd
    * /home/john

> Now , come out from the __john__ user by using the exit command and you will be logged in as a root user automatically and you can happily run the below commands .

* __Delete user__ : 
    
   * $ userdel uname  (user will be deleted but user home directory will not be deleted, you can check by ls /home)
   * $ userdel uname --remove  (user deletion + user home directory deletion)

* __Display all groups available in Linux__

   *  $ cat /etc/group

* __Create New Group__
    
   * $ groupadd group-name

* __Adding user to group__

   * $ usermod -aG group-name user-name  [-aG means addgroup]

* __Remove user from the group__
    
  * $ gpasswd -d user-name group-name

* __Display Users belongs to a group__

  * $ sudo lid -g group-name

* __Delete Group__

  * $ groupdel group-name

* __Change Group Name__  

   * $ groupmod -n new-name old-name

* __Change Username__

  * $ usermod -l new-name old-name

* __Change User password__

    * $ passwd uname

> When we create the user in linux , user will be created , group will also be created and user will be the part of that group + home directory for the user will also be created .

__Q.1 ) How can we check that a particular user belongs to how many groups ?__

__Ans.__ using id command 

__Q.2) How many users belong to a particular group ?__

__Ans.__ sudo lid -g groupname

__chown command :__ This is used for ownership change


* __Change owner of the file__

    * $ sudo chown uname <file-name/directory-name>

* __Change owner-group__

    * $ sudo chown :group-name <file-name/directory-name>

* __Change owner and group at a time__

    * $ sudo chown user:group file

> If we are giving a colon in chown command that means we are talking about the group change, otherwise user/owner change and we should execute the chown command as a root user only but in the command we are passing the “sudo “ which is fine.



## Working with zip files in Linux :


* Create few files using touch command

  * $ touch f1.txt f2.txt f3.txt

* Verify zip command is installed or not

  * $ zip -v

* Create zip with all text files

   * $ zip __zip-file-name__ *.txt

* print content of zip file

  * $ zip -sf filename

* Add new file/directory to existing zip file

   * $ zip -r __zip-name__ <file/directory>

* Delete a file from zip

  * $ zip -d __zip-file-name__ __file-name-to-delete__

* Create zip file with encryption __(setting password)__

  * $ zip -e __zip-file-name__ *.txt

* Unzip

  * $ unzip __zip-file-name__



## Package Managers in Linux :

* Pkg managers are used to install software's in Linux machines.

* __apt__ : Advanced Package Tool (debian based distributions) 

   * __sudo apt install git__

> __dpkg__ : It is underlying pkg manager used by 'apt'

* __yum__ : Yellowdog updater, modified (RED Hat based distributions) [Ex: RED Hat Linux, Amazon Linux, Centos linux]

> __dnf__ : DANDIFIED YUM (It is replacing yum package manager in latest versions of fedora and Centos)

* __Ubuntu linux__ : we should use 'apt' package manager

* __Amazon linux__ : we should use 'yum' package manager

> Update your packages first before installing any software in the Linux VM .
             
* sudo yum update 

> We can remove the software's from linux VM by running the below command
           
* sudo yum remove git 
 
* __Install Java software__

    * $ sudo yum install java

* __Install java 1.8 version__

    * $ sudo yum install java-1.8.0-openjdk

* __Install Maven software__

    *   $ sudo yum install maven

* __Install Git client__

   *   $ sudo yum install git

* __For checking the Git version__

     * $ git -v

## How to host static websites in Amazon Linux :

* Website means collection of web pages

* Websites are divided into 2 types

    * Static Website  
    * Dynamic Website

* Static websites will give same response for all users

* Dynamic Websites will give response based on logged in user

> To run a website we need a __Web Server__ [Ex: apache, httpd etc.…]

* __update the packages__

   * $ sudo yum update

* __install httpd WebServer__

    * $ sudo yum install httpd

* __Start the Service__

  * $ sudo service httpd start

> Windows runs on __RDP protocol__ , Linux machines run on __SSH protocol__ , Web Server runs on __HTTP protocol__  

> After starting httpd service, we can access our web server using EC2-VM public IP address.But we need to enable HTTP Protocol in __Security Group Inbound Rules__ to allow incoming traffic. __[This thing we are doing because we have installed our httpd server in Linux machine which is hosted on AWS]__

* After enabling HTTP protocol then access EC2-VM public IP in browser URL : http://65.1.132.215/
    
* We can modify the content of our static website by the below commands.

    * __$ cd /var/www/html__
    * __$ sudo vi index.html__

> Web Server looks for the default page name __‘index.html’__ , Write static website content in index.html & then save and close that file then access Ec2-vm public Ip via browser .


## Inode number :


=> Inode is one unique number that will be assigned for every file in Linux

=> Linux will use inode number to map our files with its name in the Linux db.

## Hard and Soft Links :


=> In linux we can create link files & we have 2 types of link files in Linux .

1)  __Hard Link__  [Exact Copy]

 
 * __Syntax To create Hard Link:__
    
    * $ __ln__ __orginal-file__ __hard-link-file__
 
    * $ touch m1.txt

    * $ ln m1.txt m11.txt
    
    > __m11.txt__ is hard link file for __m1.txt__

__$ ls -li__ : It will print the inode numbers .

> m1.txt and m11.txt files are having __same__ inode number

> If we write some data to m1.txt that data will reflect in m11.txt file also

> If we delete m1.txt file still there is no effect on m11.txt

 2) __Soft Link__   [Like a shortcut in windows OS]

 * __Syntax To create Soft Link :__
     * $ __ln -s orginal-file soft-link-file__

   * $ touch s1.txt
   * $ ln -s s1.txt s11.txt


> Original file and soft link file having __different__ inode numbers

> Data writing in original file will reflect in soft link file also

> When we remove original file then soft link file will become dangling file. We can't access that.


## Process Management :


__ps -ef__ [To check which processes are running]

__ps -ef | grep "dsf"__ [To check about the particular process/application dsf]

__kill PID__ [Give the process id , It will kill the process in the background]

 <span style="color:red;">
find . -name cbbt.csv (This command is frequently Used )
 </span>