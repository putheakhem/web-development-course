## Week I

* Introduction to Ubuntu 18.04 
* Ubuntu Basic Command
* Install PHP, Web Server, Database MySQL
* Introduction to PHP and Syntax Overview
* PHP Constant, Data Type, Variables
* PHP String
* PHP Array
* PHP If...else...elseif
* PHP Switch
* PHP For Loops
* While Loops
* PHP Function
* Lab 1. Form


> Let's get details : 

###  Introducton to Ubuntu 18.04 LTS

Introducton to Ubuntu 18.04 LTS  [here](https://wiki.ubuntu.com/BionicBeaver/ReleaseNotes)

###  Ubuntu Basic Command

> You can try 10 command line on Ubuntu 18.04 LTS  
1. sudo
This SuperUserDo is the most important command Linux newbies will use. Every single command that needs root’s permission, need this sudo command. You can use `sudo` before each command that requires root permissions –
```bash
    sudo su
```

2. ls (list)
Just like the other, you often want to see anything in your directory. With list command, the terminal will show you all the files and folders of the directory that you’re working in. Let’s say I’m in the `/home` folder and I want to see the directories & files in /home. 
```bash
    /home ls
```

3. cd
​Changing directory (cd) is the main command that always is in use in the terminal. It’s one of the most Linux basic commands. Using this is easy. Just type the name of the folder you want to go in from your current directory. If you want to go up just do it by giving double dots (..) as the parameter.
​
Let’s say I’m in /home directory and I want to move in usr directory which is always in the /home. Here is how I can use `cd` commands –

```bash 
    cd /home/username/Desktop
```

4. mkdir
Just changing directory is still incomplete. Sometimes you want to create a new folder or subfolder. You can use mkdir command to do that. Just give your folder name after mkdir command in your terminal.
```bash
    mkdir folderName
```

5. cp
copy-and-paste is the important task we need to do to organize our files. Using `cp` will help you to copy-and-paste the file from the terminal. First, you determine the file you want to copy and type the destination location to paste the file.
```bash
    cp src des
```

> Note: If you’re copying files into the directory that requires root permission for any new file, then you’ll need to use `sudo` command.  

6. rm
`rm` is a command to remove your file or even your directory. You can use `-f` if the file need root permission to be removed. And also you can use `-r` to do recursive removal to remove your folder.
```bash
    rm myfile.txt
```

7. apt-get
This command differs distro-by-distro. In Debian based Linux distributions, to install, remove and upgrade any package we’ve Advanced Packaging Tool (APT) package manager. The apt-get command will help you install the software you need to run in your Linux. It is a powerful command-line tool which can perform installation, upgrade, and even removing your software.​

```bash
sudo apt-get update
```

8. grep
You need to find a file but you don’t remember its exact location or the path. grep will help you to solve this problem. You can use the grep command to help to find the file based on given keywords.
```bash
    grep user /etc/passwd
```

9. cat
As a user, you often need to view some of text or code from your script. Again, one of the Linux basic commands is cat command. It will show you the text inside your file.
```bash
    cat CMakeLists.txt
```
10. poweroff
And the last one is `poweroff`. Sometimes you need to poweroff directly from your terminal. This command will do the task. Don’t forget to add sudo at the beginning of the command since it needs root permission to execute poweroff.

```bash
    sudo poweroff
```

### Install PHP, Web Server, Database MySQL

1. if you are on Ubuntu. Please follow [here](https://www.rosehosting.com/blog/how-to-install-php-7-3-on-ubuntu-16-04/) 
2. If you are window. Please install [Warm Server](http://www.wampserver.com/en/), [Xampp Server](https://www.apachefriends.org/index.html)

### Introduction to PHP and Syntax Overview

1. Introduction to PHP

`PHP` started out as a small open source project that evolved as more and more people found out how useful it was. Rasmus Lerdorf unleashed the `first version of PHP` way back in `1994`.
* `PHP` stand for `Hypertext Preprocessor`
* `PHP` is a server side scripting language that is embedded in HTML. It is used to manage dynamic content, databases, session, tracking, even build entire e-commerce sites. 
* It is intergrated with a number of popular databases, including MySQL, PostgreSQL, Oracle, Sybase, Informix, and Microsoft SQL Server.
* PHP suport a large number of majors protocol such as POP3, IMAP, and LDAP, from `PHP4` added support for Java and distributed ojbect architectures. 

2. Syntax Overview
The PHP parsing engine needs a way to differentiate PHP code from other elements in the page. There are four ways to do this −

    * Canonical PHP tags
    The most universally effective PHP tag style is: 

    ```bash
        <?php 
        .....
        ?>
    ```
    * Short-open tags
    Short or short-open tags look like this 
    ```bash
        <? 

        ?>
    ```
    * ASP-Style 
    ASP-style tags mimic the tag used by Active Server Pages to delineate code blocks.

    ```bash
        <% 

        %>
    ```
    * HTML script tags
    HTML script tags look like this 
    ```bash
        <script language="PHP">....</script>
    ```