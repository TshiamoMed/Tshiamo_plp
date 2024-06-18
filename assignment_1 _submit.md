[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/vbnbTt5m)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=15270571&assignment_repo_type=AssignmentRepo)
# Dev_Setup
Setup Development Environment

#Assignment: Setting Up Your Developer Environment

#Objective:
This assignment aims to familiarize you with the tools and configurations necessary to set up an efficient developer environment for software engineering projects. Completing this assignment will give you the skills required to set up a robust and productive workspace conducive to coding, debugging, version control, and collaboration.

#Tasks:

1. Select Your Operating System (OS):
   Choose an operating system that best suits your preferences and project requirements. Download and Install Windows 11. https://www.microsoft.com/software-download/windows11

   Answer : I use a linux chromebook,the first step was to enable linux by Openning Settings,Scroll down to Linux (Beta).Select Turn On. Follow the on-screen instructions to set up Linux on my Chromebook. lastly to find the operating system i ran this code ($ hostnamectl) on the linux terminal.My Operating System: Debian GNU/Linux 12 (bookworm)
The output on terminal :  

ssh25506218hc2sunacza@penguin:~$ hostnamectl
 Static hostname: penguin
       Icon name: computer-container
         Chassis: container ☐
      Machine ID: c537abf79b3d4ed19b2914cd8a655de7
         Boot ID: 0b5227e31de2432d83ed2b443c319398
  Virtualization: lxc
Operating System: Debian GNU/Linux 12 (bookworm)  
          Kernel: Linux 6.6.25-01713-g2f237acc8e50
    Architecture: x86-64

   

2. Install a Text Editor or Integrated Development Environment (IDE):
   Select and install a text editor or IDE suitable for your programming languages and workflow. Download and Install Visual Studio Code. https://code.visualstudio.com/Download



   Answer: This is what i ran to download virtual studio code,this is  the output on the terminal:

   ssh25506218hc2sunacza@penguin:~$ sudo apt update

Hit:1 https://deb.debian.org/debian bookworm InRelease
Hit:2 https://packages.microsoft.com/repos/code stable InRelease                                               
Ign:3 https://storage.googleapis.com/cros-packages/125 bookworm InRelease                                      
Ign:4 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease
Hit:5 https://storage.googleapis.com/cros-packages/125 bookworm Release
Hit:6 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Get:9 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]
Err:9 http://repo.mysql.com/apt/debian stretch InRelease                                                                                                                                                          
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Reading package lists... Done                                                                                                                                                                                     
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: https://packages.microsoft.com/repos/code/dists/stable/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.

ssh25506218hc2sunacza@penguin:~$ sudo apt install wget gpg

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
wget is already the newest version (1.21.3-1+b2).
gpg is already the newest version (2.2.40-1.1).
gpg set to manually installed.
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.

ssh25506218hc2sunacza@penguin:~$ sudo apt install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
wget is already the newest version (1.21.3-1+b2).
gpg is already the newest version (2.2.40-1.1).
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.
ssh25506218hc2sunacza@penguin:~$ sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
ssh25506218hc2sunacza@penguin:~$ sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

ssh25506218hc2sunacza@penguin:~$ sudo apt update

Hit:1 https://deb.debian.org/debian bookworm InRelease
Get:2 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]                      
Hit:3 https://packages.microsoft.com/repos/code stable InRelease                                                                                  
Ign:4 https://storage.googleapis.com/cros-packages/125 bookworm InRelease                                      
Err:2 http://repo.mysql.com/apt/debian stretch InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Ign:5 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease
Hit:6 https://storage.googleapis.com/cros-packages/125 bookworm Release
Hit:7 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Reading package lists... Done
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.

ssh25506218hc2sunacza@penguin:~$ sudo apt install code

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
The following packages will be upgraded:
  code
1 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.
Need to get 102 MB of archives.
After this operation, 2,048 B of additional disk space will be used.
Get:1 https://packages.microsoft.com/repos/code stable/main amd64 code amd64 1.90.1-1718141439 [102 MB]
Fetched 102 MB in 37s (2,767 kB/s)                                                                                                                                                                                
(Reading database ... 72902 files and directories currently installed.)
Preparing to unpack .../code_1.90.1-1718141439_amd64.deb ...
Unpacking code (1.90.1-1718141439) over (1.90.0-1717531825) ...
Setting up code (1.90.1-1718141439) ...
Processing triggers for shared-mime-info (2.2-1) ...
Processing triggers for desktop-file-utils (0.26-1) ...

ssh25506218hc2sunacza@penguin:~$ code --version

1.90.1
611f9bfce64f25108829dd295f54a6894e87339d
x64
ssh25506218hc2sunacza@penguin:~$  


3. Set Up Version Control System:
   Install Git and configure it on your local machine. Create a GitHub account for hosting your repositories. Initialize a Git repository for your project and make your first commit. https://github.com

   Answer : I installed git and configured it , below is the output of my commands copied from vis code terminal:  

ssh25506218hc2sunacza@penguin:~$ sudo apt install git

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
git is already the newest version (1:2.39.2-1.1).
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.

ssh25506218hc2sunacza@penguin:~$ cd Git

ssh25506218hc2sunacza@penguin:~/Git$ git config --global user.name "Tshiamo Medupe"

ssh25506218hc2sunacza@penguin:~/Git$ git config --global user.email "25506218@sun.ac.za"

ssh25506218hc2sunacza@penguin:~/Git$ mkdir Tshiamo_plp

ssh25506218hc2sunacza@penguin:~/Git$ cd Tshiamo_plp

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ git init

hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/ssh25506218hc2sunacza/Git/Tshiamo_plp/.git/

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ echo "# My Project" > README.md

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ ls

README.md

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ mv README.md Assignment_1

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ ls

Assignment_1

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ git add Assignment_1

ssh25506218hc2sunacza@penguin:~/Git/Tshiamo_plp$ git commit -m "Submit"

[master (root-commit) e536027] Submit
 1 file changed, 1 insertion(+)
 create mode 100644 Assignment_1

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ git remote 
set-url origin https://github.com/TshiamoMed/Tshiamo_plp

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ git push -u origin master

Username for 'https://github.com': TshiamoMed
Password for 'https://TshiamoMed@github.com': 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 285 bytes | 285.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/TshiamoMed/Tshiamo_plp
   16f33d5..79efa89  main -> main
branch 'master' set up to track 'origin/master'.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ git --version

git version 2.45.2

4. Install Necessary Programming Languages and Runtimes:
  Instal Python from http://wwww.python.org programming language required for your project and install their respective compilers, interpreters, or runtimes. Ensure you have the necessary tools to build and execute your code.

  Answer:This is the output below i got after running my codes to install python, i also installed the extenstions for python and python debugging on virtual studio code: 

  ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt update

Get:1 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]
Err:1 http://repo.mysql.com/apt/debian stretch InRelease                    
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Ign:2 https://storage.googleapis.com/cros-packages/125 bookworm InRelease
Ign:3 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease
Hit:4 https://storage.googleapis.com/cros-packages/125 bookworm Release
Hit:5 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Hit:8 https://packages.microsoft.com/repos/code stable InRelease
Hit:9 https://deb.debian.org/debian bookworm InRelease
Reading package lists... Done                     
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt install python3 python3-pip

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
python3 is already the newest version (3.11.2-1+b1).
python3-pip is already the newest version (23.0.1+dfsg-1).
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ python3 --version

Python 3.11.2

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ pip3 --version

pip 23.0.1 from /usr/lib/python3/dist-packages/pip (python 3.11)

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ 


5. Install Package Managers:
   If applicable, install package managers like pip (Python).

answer: i installed python and pip at the same time : 

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ pip3 --version

pip 23.0.1 from /usr/lib/python3/dist-packages/pip (python 3.11)

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ 

6. Configure a Database (MySQL):
   Download and install MySQL database. https://dev.mysql.com/downloads/windows/installer/5.7.html

   Answer:below is the output after running the codes to install mysql:

   ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt update

Hit:1 https://deb.debian.org/debian bookworm InRelease
Hit:2 https://packages.microsoft.com/repos/code stable InRelease                                               
Ign:3 https://storage.googleapis.com/cros-packages/125 bookworm InRelease                                      
Ign:4 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease 
Hit:5 https://storage.googleapis.com/cros-packages/125 bookworm Release
Hit:6 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Get:7 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]
Err:7 http://repo.mysql.com/apt/debian stretch InRelease                                                                                                                                                          
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Reading package lists... Done                                                                                                                                                                                     
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt upgrade

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
The following packages will be upgraded:
  dart
1 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Need to get 157 MB of archives.
After this operation, 17.4 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 https://storage.googleapis.com/download.dartlang.org/linux/debian stable/main amd64 dart amd64 3.4.4-1 [157 MB]
Fetched 157 MB in 1min 22s (1,909 kB/s)                                                                                                                                                                           
(Reading database ... 72902 files and directories currently installed.)
Preparing to unpack .../dart_3.4.4-1_amd64.deb ...
Unpacking dart (3.4.4-1) over (3.4.3-1) ...
Setting up dart (3.4.4-1) ...
ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt install mysql-server
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package mysql-server is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'mysql-server' has no installation candidate

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ mysql --version

mysql  Ver 15.1 Distrib 10.11.6-MariaDB, for debian-linux-gnu (x86_64) using  EditLine wrapper

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt install mysql-client

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package mysql-client is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'mysql-client' has no installation candidate

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user. If you've just installed MariaDB, and
haven't set the root password yet, you should just press enter here.

Enter current password for root (enter for none): 
OK, successfully used password, moving on...

Setting the root password or using the unix_socket ensures that nobody
can log into the MariaDB root user without the proper authorisation.

You already have your root account protected, so you can safely answer 'n'.

Switch to unix_socket authentication [Y/n] n
 ... skipping.

You already have your root account protected, so you can safely answer 'n'.

Change the root password? [Y/n] n
 ... skipping.

By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] n
 ... skipping.

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo systemctl status mysql

● mariadb.service - MariaDB 10.11.6 database server
     Loaded: loaded (/lib/systemd/system/mariadb.service; enabled; preset: enabled)
    Drop-In: /run/systemd/system/service.d
             └─zzz-lxc-service.conf
     Active: active (running) since Mon 2024-06-17 10:38:37 SAST; 2h 7min ago
       Docs: man:mariadbd(8)
             https://mariadb.com/kb/en/library/systemd/
    Process: 142 ExecStartPre=/usr/bin/install -m 755 -o mysql -g root -d /var/run/mysqld (code=exited, status=0/SUCCESS)
    Process: 159 ExecStartPre=/bin/sh -c systemctl unset-environment _WSREP_START_POSITION (code=exited, status=0/SUCCESS)
    Process: 172 ExecStartPre=/bin/sh -c [ ! -e /usr/bin/galera_recovery ] && VAR= ||   VAR=`cd /usr/bin/..; /usr/bin/galera_recovery`; [ $? -eq 0 ]   && systemctl set-environment _WSREP_START_POSITION=$VAR || >
    Process: 328 ExecStartPost=/bin/sh -c systemctl unset-environment _WSREP_START_POSITION (code=exited, status=0/SUCCESS)
    Process: 332 ExecStartPost=/etc/mysql/debian-start (code=exited, status=0/SUCCESS)
   Main PID: 186 (mariadbd)
     Status: "Taking your SQL requests now..."
      Tasks: 9 (limit: 3298)
     Memory: 99.2M
     CGroup: /system.slice/mariadb.service
             └─186 /usr/sbin/mariadbd

Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] InnoDB: File './ibtmp1' size is now 12.000MiB.
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] InnoDB: log sequence number 46846; transaction id 14
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] Plugin 'FEEDBACK' is disabled.
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] InnoDB: Buffer pool(s) load completed at 240617 10:38:37
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] Server socket created on IP: '0.0.0.0'.
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] Server socket created on IP: '::'.
Jun 17 10:38:37 penguin mariadbd[186]: 2024-06-17 10:38:37 0 [Note] /usr/sbin/mariadbd: ready for connections.
Jun 17 10:38:37 penguin mariadbd[186]: Version: '10.11.6-MariaDB-0+deb12u1'  socket: '/run/mysqld/mysqld.sock'  port: 3306  Debian 12
Jun 17 10:38:37 penguin systemd[1]: Started mariadb.service - MariaDB 10.11.6 database server.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ 

7. Set Up Development Environments and Virtualization (Optional):
   Consider using virtualization tools like Docker or virtual machines to isolate project dependencies and ensure consistent environments across different machines.

   answer: below is the output after running my codes to install docker:

   ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt update

Hit:1 https://deb.debian.org/debian bookworm InRelease
Hit:2 https://packages.microsoft.com/repos/code stable InRelease                                             
Get:3 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]                                           
Ign:4 https://storage.googleapis.com/cros-packages/125 bookworm InRelease
Ign:5 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease
Hit:6 https://storage.googleapis.com/cros-packages/125 bookworm Release
Err:3 http://repo.mysql.com/apt/debian stretch InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Hit:7 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Reading package lists... Done
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
ca-certificates is already the newest version (20230311).
curl is already the newest version (7.88.1-10+deb12u5).
software-properties-common is already the newest version (0.99.30-4).
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  apt-transport-https
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 25.2 kB of archives.
After this operation, 35.8 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 https://deb.debian.org/debian bookworm/main amd64 apt-transport-https all 2.6.1 [25.2 kB]
Fetched 25.2 kB in 0s (81.7 kB/s)              
Selecting previously unselected package apt-transport-https.
(Reading database ... 72902 files and directories currently installed.)
Preparing to unpack .../apt-transport-https_2.6.1_all.deb ...
Unpacking apt-transport-https (2.6.1) ...
Setting up apt-transport-https (2.6.1) ...

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt update
Get:1 http://repo.mysql.com/apt/debian stretch InRelease [21.6 kB]
Get:2 https://download.docker.com/linux/debian bookworm InRelease [43.3 kB]                                                                                                                    
Hit:3 https://deb.debian.org/debian bookworm InRelease                                                                                                            
Hit:4 https://packages.microsoft.com/repos/code stable InRelease                                                                        
Err:1 http://repo.mysql.com/apt/debian stretch InRelease                                                                                
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
Ign:5 https://storage.googleapis.com/cros-packages/125 bookworm InRelease
Ign:6 https://storage.googleapis.com/download.dartlang.org/linux/debian stable InRelease
Get:7 https://download.docker.com/linux/debian bookworm/stable amd64 Packages [24.3 kB]
Hit:8 https://storage.googleapis.com/cros-packages/125 bookworm Release
Hit:10 https://storage.googleapis.com/download.dartlang.org/linux/debian stable Release
Reading package lists... Done
W: http://repo.mysql.com/apt/debian/dists/stretch/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: GPG error: http://repo.mysql.com/apt/debian stretch InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 8C718D3B5072E1F5
E: The repository 'http://repo.mysql.com/apt/debian stretch InRelease' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
W: https://deb.debian.org/debian/dists/bookworm/InRelease: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.
W: https://storage.googleapis.com/cros-packages/125/dists/bookworm/Release.gpg: The key(s) in the keyring /etc/apt/trusted.gpg.d/mysql.gpg are ignored as the file has an unsupported filetype.

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo apt install docker-ce

Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libpfm4 libz3-dev llvm-14 llvm-14-runtime llvm-14-tools python3-pygments python3-yaml
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  apparmor containerd.io docker-buildx-plugin docker-ce-cli docker-ce-rootless-extras docker-compose-plugin libltdl7 libslirp0 pigz slirp4netns
Suggested packages:
  apparmor-profiles-extra apparmor-utils aufs-tools cgroupfs-mount | cgroup-lite
The following NEW packages will be installed:
  apparmor containerd.io docker-buildx-plugin docker-ce docker-ce-cli docker-ce-rootless-extras docker-compose-plugin libltdl7 libslirp0 pigz slirp4netns
0 upgraded, 11 newly installed, 0 to remove and 0 not upgraded.
Need to get 122 MB of archives.
After this operation, 437 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 https://deb.debian.org/debian bookworm/main amd64 pigz amd64 2.6-1 [64.0 kB]
Get:2 https://download.docker.com/linux/debian bookworm/stable amd64 containerd.io amd64 1.6.33-1 [30.0 MB]
Get:3 https://deb.debian.org/debian bookworm/main amd64 apparmor amd64 3.0.8-3 [616 kB]
Get:4 https://deb.debian.org/debian bookworm/main amd64 libltdl7 amd64 2.4.7-5 [393 kB]
Get:5 https://deb.debian.org/debian bookworm/main amd64 libslirp0 amd64 4.7.0-1 [63.0 kB]
Get:6 https://deb.debian.org/debian bookworm/main amd64 slirp4netns amd64 1.2.0-1 [37.5 kB]
Get:7 https://download.docker.com/linux/debian bookworm/stable amd64 docker-buildx-plugin amd64 0.14.1-1~debian.12~bookworm [29.6 MB]                                                                             
Get:8 https://download.docker.com/linux/debian bookworm/stable amd64 docker-ce-cli amd64 5:26.1.4-1~debian.12~bookworm [14.6 MB]                                                                                  
Get:9 https://download.docker.com/linux/debian bookworm/stable amd64 docker-ce amd64 5:26.1.4-1~debian.12~bookworm [25.3 MB]                                                                                      
Get:10 https://download.docker.com/linux/debian bookworm/stable amd64 docker-ce-rootless-extras amd64 5:26.1.4-1~debian.12~bookworm [9,316 kB]                                                                    
Get:11 https://download.docker.com/linux/debian bookworm/stable amd64 docker-compose-plugin amd64 2.27.1-1~debian.12~bookworm [12.5 MB]                                                                           
Fetched 122 MB in 1min 7s (1,823 kB/s)                                                                                                                                                                            
Preconfiguring packages ...
Selecting previously unselected package pigz.
(Reading database ... 72906 files and directories currently installed.)
Preparing to unpack .../00-pigz_2.6-1_amd64.deb ...
Unpacking pigz (2.6-1) ...
Selecting previously unselected package apparmor.
Preparing to unpack .../01-apparmor_3.0.8-3_amd64.deb ...
Unpacking apparmor (3.0.8-3) ...
Selecting previously unselected package containerd.io.
Preparing to unpack .../02-containerd.io_1.6.33-1_amd64.deb ...
Unpacking containerd.io (1.6.33-1) ...
Selecting previously unselected package docker-buildx-plugin.
Preparing to unpack .../03-docker-buildx-plugin_0.14.1-1~debian.12~bookworm_amd64.deb ...
Unpacking docker-buildx-plugin (0.14.1-1~debian.12~bookworm) ...
Selecting previously unselected package docker-ce-cli.
Preparing to unpack .../04-docker-ce-cli_5%3a26.1.4-1~debian.12~bookworm_amd64.deb ...
Unpacking docker-ce-cli (5:26.1.4-1~debian.12~bookworm) ...
Selecting previously unselected package docker-ce.
Preparing to unpack .../05-docker-ce_5%3a26.1.4-1~debian.12~bookworm_amd64.deb ...
Unpacking docker-ce (5:26.1.4-1~debian.12~bookworm) ...
Selecting previously unselected package docker-ce-rootless-extras.
Preparing to unpack .../06-docker-ce-rootless-extras_5%3a26.1.4-1~debian.12~bookworm_amd64.deb ...
Unpacking docker-ce-rootless-extras (5:26.1.4-1~debian.12~bookworm) ...
Selecting previously unselected package docker-compose-plugin.
Preparing to unpack .../07-docker-compose-plugin_2.27.1-1~debian.12~bookworm_amd64.deb ...
Unpacking docker-compose-plugin (2.27.1-1~debian.12~bookworm) ...
Selecting previously unselected package libltdl7:amd64.
Preparing to unpack .../08-libltdl7_2.4.7-5_amd64.deb ...
Unpacking libltdl7:amd64 (2.4.7-5) ...
Selecting previously unselected package libslirp0:amd64.
Preparing to unpack .../09-libslirp0_4.7.0-1_amd64.deb ...
Unpacking libslirp0:amd64 (4.7.0-1) ...
Selecting previously unselected package slirp4netns.
Preparing to unpack .../10-slirp4netns_1.2.0-1_amd64.deb ...
Unpacking slirp4netns (1.2.0-1) ...
Setting up apparmor (3.0.8-3) ...
Created symlink /etc/systemd/system/sysinit.target.wants/apparmor.service → /lib/systemd/system/apparmor.service.
Setting up docker-buildx-plugin (0.14.1-1~debian.12~bookworm) ...
Setting up containerd.io (1.6.33-1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Setting up docker-compose-plugin (2.27.1-1~debian.12~bookworm) ...
Setting up libltdl7:amd64 (2.4.7-5) ...
Setting up docker-ce-cli (5:26.1.4-1~debian.12~bookworm) ...
Setting up libslirp0:amd64 (4.7.0-1) ...
Setting up pigz (2.6-1) ...
Setting up docker-ce-rootless-extras (5:26.1.4-1~debian.12~bookworm) ...
Setting up slirp4netns (1.2.0-1) ...
Setting up docker-ce (5:26.1.4-1~debian.12~bookworm) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /lib/systemd/system/docker.socket.
Processing triggers for man-db (2.11.2-2) ...
Processing triggers for libc-bin (2.36-9+deb12u7) ...

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ sudo systemctl status docker

● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; preset: enabled)
    Drop-In: /run/systemd/system/service.d
             └─zzz-lxc-service.conf
     Active: active (running) since Mon 2024-06-17 12:55:39 SAST; 1min 8s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 14927 (dockerd)
      Tasks: 9
     Memory: 110.6M
     CGroup: /system.slice/docker.service
             └─14927 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Jun 17 12:55:36 penguin dockerd[14927]: time="2024-06-17T12:55:36.713655347+02:00" level=info msg="Loading containers: start."
Jun 17 12:55:36 penguin dockerd[14927]: time="2024-06-17T12:55:36.792925998+02:00" level=warning msg="Running modprobe bridge br_netfilter failed with message: , error: exec: \"modprobe\": executable file not f>
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.347352479+02:00" level=info msg="Loading containers: done."
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.644386696+02:00" level=warning msg="Not using native diff for overlay2, this may cause degraded performance for building images: running in a us>
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.644761227+02:00" level=warning msg="WARNING: bridge-nf-call-iptables is disabled"
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.644785405+02:00" level=warning msg="WARNING: bridge-nf-call-ip6tables is disabled"
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.644872551+02:00" level=info msg="Docker daemon" commit=de5c9cf containerd-snapshotter=false storage-driver=overlay2 version=26.1.4
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.645672862+02:00" level=info msg="Daemon has completed initialization"
Jun 17 12:55:39 penguin systemd[1]: Started docker.service - Docker Application Container Engine.
Jun 17 12:55:39 penguin dockerd[14927]: time="2024-06-17T12:55:39.730475767+02:00" level=info msg="API listen on /run/docker.sock"

ssh25506218hc2sunacza@penguin:~/ Git/Tshiamo_plp$ 

8. Explore Extensions and Plugins:
   Explore available extensions, plugins, and add-ons for your chosen text editor or IDE to enhance functionality, such as syntax highlighting, linting, code formatting, and version control integration.

   answer:I opened Virtual studio code application , went under extention, i installed and enabled the following extentions : Python (for Python support)
GitLens (for Git integration)
Prettier (for code formatting)
ESLint (for linting)
flutter 
django 
dart
mysql
python debugger
code runner
code debugger 

9.reflection :

Answer:  
I encountered a few issues while setting up MySQL and Docker on my Debian-based system. Let's address them step by step.

Issue with MySQL Installation:
Missing MySQL Server Package:
When i tried to install MySQL Server (mysql-server), it wasn't available in the repositories. Instead, my system installed MariaDB (mariadb-server). This is a common substitution on Debian-based systems because MariaDB aims to be a drop-in replacement for MySQL.

Solution: Since i already have MariaDB installed and running (mariadb.service is active), i can proceed with using MariaDB instead of MySQL. They are functionally very similar, and for most purposes, MariaDB is interchangeable with MySQL.
Error with MySQL Client Installation:
Similarly, i encountered issues installing mysql-client, which suggests it's not available in my current repository setup.

Solution: MariaDB uses mysql-client as its client tool. The command mysql i used is from MariaDB, which means i can continue using mysql as i would with MySQL.
Issue with Docker Installation:
GPG Key Error:
During Docker installation, i received warnings about GPG key verification for the Docker repository.

Solution: i successfully installed Docker despite the warning. This issue usually arises from missing or outdated GPG keys. i can often resolve this by updating my GPG keys manually, but it shouldn't affect Docker's functionality after installation.
Recommendations for Moving Forward:
Database Management: Since i have MariaDB installed and secured (sudo mysql_secure_installation), i can proceed with using it for my database needs. The commands like mysql and sudo systemctl status mariadb will work as expected.

Docker Usage: Docker was successfully installed (sudo systemctl status docker shows it's active), allowing me to create and manage containers. i can proceed with setting up development environments using Docker containers.

Development Isolation: Consider using Docker for isolating development environments, which helps in managing dependencies and ensuring consistent setups across different machines.

In summary, while i encountered some repository and package naming discrepancies, i have successfully set up MariaDB and Docker. These tools should now be ready for my development and database management needs.

Finally the link tomy github repository is : git@github.com:TshiamoMed/Tshiamo_plp.git

9. Document Your Setup:
    Create a comprehensive document outlining the steps you've taken to set up your developer environment. Include any configurations, customizations, or troubleshooting steps encountered during the process. 

#Deliverables:
- Document detailing the setup process with step-by-step instructions and screenshots where necessary.
- A GitHub repository containing a sample project initialized with Git and any necessary configuration files (e.g., .gitignore).
- A reflection on the challenges faced during setup and strategies employed to overcome them.

#Submission:
Submit your document and GitHub repository link through the designated platform or email to the instructor by the specified deadline.

#Evaluation Criteria:**
- Completeness and accuracy of setup documentation.
- Effectiveness of version control implementation.
- Appropriateness of tools selected for the project requirements.
- Clarity of reflection on challenges and solutions encountered.
- Adherence to submission guidelines and deadlines.

Note: Feel free to reach out for clarification or assistance with any aspect of the assignment.

