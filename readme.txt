                                                  GIT   
==============================================================================================================


Devops/Platform Engineer::                       SRE(Site Reliability Engineer:   
============================                     ==================================
1. Managing the tools stack                      1.Monitoring
2. Security                                      2.System uptime
3. Reliability of tools                          3.Coding
4. Integration of the tools                      4.Site reliability enginerring
5. Efficiceny                                    5.Oncall activities
     |                                                  |
(Pre Deployment)=========================|=====================(Post Deployment)
                                         |
==========================================================================================================
|           |             |      |                |               |            |           |           |          
Tools Linux/networking  cloud  scability   coding(pythong)    efficiency monitoring   Reliablity   AWS/AZURE
    

Tech Stack that i will cover in Devops
==========================================
              |====Git/Github        
              |====Linux            |----Trivy
              |====Security-------- |----SonarQube
              |                     |----Blackduck
              |                     |----Fortify
              |====CICD------> Jenkins/ArgoCD
              |====Containerzation------> Docker
              |====Orchestration--------> Kubernets
              |=====Cloud----------------> AWS/AZURE
              |=====Automation-----------> Python/Shell
              |=====Coding----------------> Python
              |=====Monitoring ----------->|-- Prometheus
                                           |-- Grapahana
                                           |-- kiale/Istio
                                           |-- Joeger
                                           |-- Splunk
              |=====IAC--------------------> Terraform
              |=====Repository-------------> Jfrog/Dockerhub/ECR
              |=====ConfigurationManagement-> Ansible
              |=====JAVA/POM.XML/DEPENDENCY Check
              |=====Github actions/Maven Tool
              |=====Helm
              |=====Database----------------> Mysql


Branching Stragies:
========================

To create a new repository on the command line:
--------------------------------------------------

echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/akhilgit19/test.git
git push -u origin main

push an existing repository from the command line
------------------------------------------------------
git remote add origin https://github.com/akhilgit19/test.git
git branch -M main
git push -u origin main


Git basic Commands:
=======================
1.git init <directory>-  Create empty git repo in specified directory with no argument to initialize the current 
                         directory.
2.git clone <repo>-  Clone repo located at <repo> onto local mahcine.Original repo can be located on the local 
                     filesystem.
3.git config user.name <name>- Define author name to used for all commits in current repo.Devs commonly use -- 
                               global flag to set config options for current user.
4.git add . - Stage all changes in<directory> for the next commit.
5.git commit -m "<message>"- Commit the staged snapshot, but instead of launching a text editor,use<message> as the 
               commit message.
6.git status - List which files are staged,unstaged, and untracked.
7.git log    - Display the entire commit history using the default format.
8.git diff   - show unstaged changes between your index and working directory

Git Undoing Changes Commands
---------------------------------
9.git revert <commit>  - Create new commit that undoes all the changes made in <commit>, then apply it to the 
                       current batch
10.git reset <file>  - Remote<file> from the staging area,but leave the working directory unchanged.This unstages a 
                       file without overwriting any changes.
11.git  clean -n - Shows which files would be removed from working directory. Use the -f flag in place of the -n 
                   flag to execute the clean

Rewriting Git History Commands
----------------------------------
12.git commit --amend - Replace the last commit with the staged changes and last commit combined.Use with the 
                        nothing staged to edit the last commit's message
   
13.git rebase <base>- Rebase the current branch onto<base>.<base> can be a commit ID, branch name, a tag, or a 
                      relative reference to HEAD.
14.git reflog - show a log of changes to the local repository's HEAD.
                Add --relative-date flag to show date info or --all to show all refs.

Git Branches commands
-----------------------------------
15.git branch -a - List all of the branches in your repo.Add a <branch> argument to create a new branch with the 
                   name<branch>.
16.git checkout -b <branch_name> - Create and check out a new branch named <branch>. Drop the -b flag to checkout 
                                   an existing branch
17.git merge <branch> - Merge<branch> into the current branch.

Remote Repositories Commands
----------------------------
18. git remote add <name> <url>- Create a new connection to a remote repo. After adding a remote,you can use,<name> 
                                 as a shortcut for <url> in other commands.
19. git fetch <remote> <branch>- Fetches a specific <branch>, from the repo.Leave off<branch> to fetch all 
                                 remote refs.
20. git pull <remote>- Fetch the specified remote's copy of current branch and immediately merge it into the local 
                       copy.(To get the difference of changes in the respository)
21. git push <remote> <branch>- Push the branch to <remote> along with necessary commits and object.Creates names 
                                branch in the remote repo if it doesn't exit.

Addtional Options Git Commands
--------------------------------
GIT CONFIG
--------------
22. git config --global user.name <name>- Define the author name to be used for all commits by the current user.

23.git config --global user.email <email>- Define the author email to be used for all commits by the current user.
24.git config --global alias. <alias-name> <git-command>- Create shortcut for a Git command. 
            E.g. alias.glog “log --graph --oneline” will set ”git glog” equivalent to ”git log --graph--oneline.
25.git config --system core.editor <editor>-Set text editor used by commands for all users on the machine. <editor>
                                            arg should be the command that launches the desired editor (e.g., vi).
26.git config --global --edit - Open the global configuration file in a text editor for manual editing.


Git Log:
---------
27. git log -<limit>-  Limit number of commits by <limit>. E.g. ”git log -5” will limit to 5 commits.
28. git log --oneline - Condonse each commit to a single line
29. git log -p - Display the full diff of each commit.
30. git log --stat -Include which files were altered and the relative number of lines that were added or deleted from each 
                    of them.

31. git log -p -Display the full diff of each commit.
32 git log --author=”<pattern>” -Search for commits by a particular author.

33.git log --grep=”<pattern>” -Search for commits with a commit message that matches <pattern>.
34. git log <since>..<until> -Show commits that occur between <since> and <until>. Args can be a commit ID, branch name, 
                              HEAD, or any other kind of revision reference.

35.git log -- <file> -Only display commits that have the specified file.
36.git log --graph --decorate  --graph flag draws a text based graph of commits on left side of commit
                               msgs. --decorate adds names of branches or tags of commits shown.

Git Diff
------------
37.git diff HEAD  -Show difference between working directory and last commit.
38.git diff --cached  -Show difference between staged changes and last commit

GIT RESET
-------------
38.git reset -Reset staging area to match most recent commit, but leave the working directory unchanged.
39.git reset --hard -Reset staging area and working directory to match most recent commit and overwrites all changes in the 
                     working directory.
40.git reset <commit> - Move the current branch tip backward to <commit>, reset the staging area to match, but leave the 
                        working directory alone.
41.git reset --hard <commit> -Same as previous, but resets both the staging area & working directory to
                              match. Deletes uncommitted changes, and all commits after <commit>.
   git reset --hard HEAD~1

GIT REBASE
-----------
42.git rebase -i <base> -Interactively rebase current branch onto <base>. Launches editor to enter
                         commands for how each commit will be transferred to the new base.

43.git pull --rebase <remote> -Fetch the remote’s copy of current branch and rebases it into the local
                               copy. Uses git rebase instead of merge to integrate the branches.

GIT PUSH
--------
44.git push <remote> --force -Forces the git push even if it results in a non-fast-forward merge. Do not use
                              the --force flag unless you’re absolutely sure you know what you’re doing.

45.git push <remote> --all  -Push all of your local branches to the specified remote

46.git push <remote> --tags -Tags aren’t automatically pushed when you push a branch or use the
                            --all flag. The --tags flag sends all of your local tags to the remote repo.




14.git cherypick
15.git fetch

17.git revert
18.git switch  branch_name
19.git branch -d branch_name



Git Automation:
-----------------
https://docs.github.com/en/rest/branches?apiVersion=2022-11-28
https://github.com/praveen1994dec/Knowledge_Base/blob/main/Jenkins/Jenkins%20Notes.pdf

Github rest API'S
--------------------


Example:

Code:
------
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/branches

Response:
----------
akhilpagadapoola@Akhils-MacBook-Air prime10devops % curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer $GITHUB_TOKEN" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/branches

[
  {
    "name": "gitdocuments",
    "commit": {
      "sha": "e238e759993499e527b1652c475a0213132cd640",
      "url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/commits/e238e759993499e527b1652c475a0213132cd640"
    },
    "protected": false,
    "protection": {
      "enabled": false,
      "required_status_checks": {
        "enforcement_level": "off",
        "contexts": [

        ],
        "checks": [

        ]
      }
    },
    "protection_url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/branches/gitdocuments/protection"
  },
  {
    "name": "jenkins",
    "commit": {
      "sha": "ab20fe86ade9fb4993f8a6285e151fba2dd10801",
      "url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/commits/ab20fe86ade9fb4993f8a6285e151fba2dd10801"
    },
    "protected": false,
    "protection": {
      "enabled": false,
      "required_status_checks": {
        "enforcement_level": "off",
        "contexts": [

        ],
        "checks": [

        ]
      }
    },
    "protection_url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/branches/jenkins/protection"
  },
  {
    "name": "main",
    "commit": {
      "sha": "e3e96c6b4ad9fb8d98dc15b64a89e08a0eaa127a",
      "url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/commits/e3e96c6b4ad9fb8d98dc15b64a89e08a0eaa127a"
    },
    "protected": false,
    "protection": {
      "enabled": false,
      "required_status_checks": {
        "enforcement_level": "off",
        "contexts": [

        ],
        "checks": [

        ]
      }
    },
    "protection_url": "https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/branches/main/protection"
  }
]




                                                     LINUX
==============================================================================================================


         
     SSL/TLS                UDP/TCP/
User-------------> Request------------------> Regional server---------> DNS Server

Important networking tools for Devops Engineering
=======================================================
1.PING Command: ping google.com   - Purpose to check the reachability of a host on an Internet Protocol(IP)
====================================
akhilpagadapoola@Akhils-MacBook-Air Jenkins % ping google.com
PING google.com (142.250.193.46): 56 data bytes
64 bytes from 142.250.193.46: icmp_seq=0 ttl=112 time=56.100 ms
64 bytes from 142.250.193.46: icmp_seq=1 ttl=112 time=53.291 ms
64 bytes from 142.250.193.46: icmp_seq=2 ttl=112 time=51.908 ms

2.Traceroute Command:  traceroute google.com - To display the routee and measue transit delays of packets across an Internet Protocol network
============================================
akhilpagadapoola@Akhils-MacBook-Air Jenkins % traceroute google.com 
traceroute to google.com (142.250.192.206), 64 hops max, 52 byte packets
 1  reliance.reliance (192.168.29.1)  9.278 ms  4.754 ms  4.402 ms
 2  10.14.240.1 (10.14.240.1)  9.956 ms  9.464 ms  8.910 ms
 3  172.31.2.102 (172.31.2.102)  18.370 ms
    172.31.2.120 (172.31.2.120)  21.698 ms  21.247 ms
 4  192.168.59.122 (192.168.59.122)  16.644 ms
    192.168.59.120 (192.168.59.120)  33.227 ms
    192.168.59.124 (192.168.59.124)  23.655 ms

3.Netstat Command: netstat -a-- To display active network connections,routingtables, interface statistics,
==================================   masquerade connections, and multicast membership

akhilpagadapoola@Akhils-MacBook-Air Jenkins % netstat -a
Active Internet connections (including servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)    
tcp4       0      0  192.168.29.120.60146   lb-140-82-113-25.https ESTABLISHED
tcp6       0      0  2405:201:c01d:f8.60047 sd-in-f188.1e100.5228  ESTABLISHED
tcp6       0      0  akhils-macbook-a.60003 fe80::44:eca7:f2.62327 ESTABLISHED
tcp6       0      0  2405:201:c01d:f8.60006 2620:1ec:21::14.https  ESTABLISHED
tcp6       0      0  *.60003                *.*                    LISTEN     
tcp4       0      0  *.60003                *.*                    LISTEN     
tcp6       0      0  akhils-macbook-a.black fe80::106:29a6:6.1026  ESTABLISHED
tcp6       0      0  akhils-macbook-a.1024  fe80::106:29a6:6.1024  ESTABLISHED

4.Nmap Command: nmap -p 1-1000 target -Purpose: To discover hosts and services on a computer network creating  a map of the network.
================================================

5.Tcpdump command :tcpdump -i eth0 - purpose: To capture and analyze network traffic. TCP- Transmission control protocol
=====================================
UDP- User data protocol

6.Ipconfig( Window)/ifconfig(Linux)- To display the configuration of network interfaces
==================================================

7. Dig(Domain information Groper): dig google.com
=======================================
Purpose: To query DNS name servers for information about host addresses,mail exchange,
name server and related information

8.Nslookup:(Windows)/host(Linux)- To query DNS server for domain information
=====================================


Linux Network Protocols:
=============================
FTP-File transfer Protocol(TCP --20,21)
SSH-Secure Shell SSH Securee login (TCP-22)
Telnet- remote login service, unencrypted text message(23)
SMTP-Simple Mail Transfer Protocol E mail routing (TCP-25)
DNS- Domain Name System( TCP/UDP-53)
DHCP- Dyanmic Host Configuration Protocol IP-(67server)-68(client).
HTTP-Hypertext Transfer Protocol (TCP-80) used in the world wide web(TCP-80)
POP3- Post office protocol POP3(TCP-110)
NTP-Network Tim Protocol(UDP-123)
SNMP-Simple Network Management Protocol(UDP-161/162)
HTTPS-Secure (HTTPS) HTTP over TLS/SSL(TCP-443)



Linux Commands:
=================
User and file management:
============================
1. uname  
================
   -a: print all system information
   -s: print the kernel name
   -r: print the kernel release
   -m: print the machine hardware name
a
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uname
Darwin
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uname -a
Darwin Akhils-MacBook-Air.local 23.1.0 Darwin Kernel Version 23.1.0: Mon Oct  9 21:28:12 PDT 2023; root:xnu-10002.41.9~6/RELEASE_ARM64_T8103 arm64
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uname -s
Darwin
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uname -r
23.1.0
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uname -m
arm64
akhilpagadapoola@Akhils-MacBook-Air prime10devops %

2. uptime:
==============
The command display how long the system has been running and  the current system load average
akhilpagadapoola@Akhils-MacBook-Air prime10devops % uptime
11:01  up 4 days, 21:31, 2 users, load averages: 1.79 2.19 2.22


3. date:
==========
akhilpagadapoola@Akhils-MacBook-Air prime10devops % date
Thu Jan 16 11:02:09 IST 2025

4.who:
========
This command display information about current logged in users.
It shows the username, terminal,login time and source IP address

akhilpagadapoola@Akhils-MacBook-Air prime10devops % who
akhilpagadapoola console      Jan 11 13:31 
akhilpagadapoola ttys000      Jan 13 10:01 


5.whoami
===========
This command prints the username of the current user
akhilpagadapoola@Akhils-MacBook-Air prime10devops % whoami
akhilpagadapoola

6. which:
=============
This command display the full path to the executabe file of a given command
It helps to identify the location of a command executable file in the systems path
environment variable

Example: which is displays the path to the is command

Imp directories in lin
=======================
/bin- software binary
/etc- programe files
/var- log files
/home- home folder for user
/lib- library foler for user
/sbin- superior bin files
/opt- application folder/ 

7. id:
=======
This command display the user and group IDs of the current user or a specified user.

akhilpagadapoola@Akhils-MacBook-Air prime10devops % id
uid=501(akhilpagadapoola) gid=20(staff) groups=20(staff),12(everyone),61(localaccounts),79(_appserverusr),80(admin),81(_appserveradm),98(_lpadmin),701(com.apple.sharepoint.group.1),33(_appstore),100(_lpoperator),204(_developer),250(_analyticsusers),395(com.apple.access_ftp),101(com.apple.access_screensharing-disabled),399(com.apple.access_ssh),400(com.apple.access_remote_ae)


8. sudo:
=========
 This command allows users to execute commands with the privileges of another user


9. shutdown and reboot:
=============================
shutdown
reboot

10.Linux pacakges 
=============================
Ubuntu: apt
Centos: yum 
Windows: .exe

Example: sudo apt-get update
         sudo apt-get install docker.io -y

11. CAT command:
=====================
it will show list of user

cat /etc/passwd

12.Types of login:
====================
bash,
ksh(cronshell),
login,
sh(shell)


User and group managemen commands"
======================================================
1. sudo useradd -m pardeep
2. whoami
3. sudo passwd pardeep
4. su pardeep (switch user)
5. sudo userdel pardeep
6. sudo groupadd 
7. sudo gpasswd -a username groupname, To set the group password --gpasswd groupname, 
   To make a user the group's owner- gpasswd -m username groupname

8. r- reasd
   w- write
   x- execute

9. umask 022
   defualt permission in linux system for files -666 folders-777
   if we give umask 022  subtract from default permissions files 622 folders 755

10. zip: zip -r ldf.zip document
                laf.tar 
     -cvzf 
      c-compress
      v-verboze
      z-zip
      f-filename


11. wget and curl are command line tools used for downloading files from remote server.


                                                            Jenkins
==============================================================================================================

1.Jenkins file is like configuration file.

                                        WalmartApplication
===============================================================================================
|               |            |           |             |              |       |                |
cicd     securitytools   buildtools artifactory  Infractureascode  docker     k8        MonitoringSRE



Architecure:                   
==============                                                   Image
                                                                  |
                                           Jfrog/Nexus            |
                                     (stores binary file)         |
                                           |(tools)               |
Checkout-----> secrutiy ---> build ---->aritfactory---> IAC---> docker---> k8
                  |(tools)      |
                  |             |          |------- Java ----------> POM.XML---> Maven
                checkmarks     maven       | 
                blackduck       |(tools)---|------- Nodejs/React---> Package.json----> nmp/node
                 sonarqube                 |   
                 fortify                   |------- android--------->-build.gridle-->gridle
                 owasp                     |------- python---------->req.txt ----->python 
               

Below is  groovy code.

pipeline{
   agent any{
        environment variables{
              parameters{
                     choice="value=terraform": yes/no
                     string=" 
                     stages{
                          stage{
                             script{
                                 code in block




Build toos:
================
Java -----> POM.XML---> Maven
Nodejs/React---> Package.json----> nmp/node
android--------->build.gridle-->gridle
python--------->req.txt ----->python


Imp dependencides in Pom.xml ---groupid.arificatid.version.packaging
===============================
ex:
====
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.2.1.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
    <groupId>com.minikube.sample</groupId>
    <artifactId>kubernetes-configmap-reload</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>jar</packaging>
    <name>minikube-sample</name>
    <description>Demo project for Spring Cloud Kubernetes</description>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
        <java.version>1.8</java.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-kubernetes-config</artifactId>
            <version>1.1.0.RELEASE</version>
        </dependency>

        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.20</version>
            <scope>provided</scope>
        </dependency>


        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
        <dependency>
            <groupId>org.springframework.security</groupId>
            <artifactId>spring-security-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
                 <plugin>
              <groupId>org.apache.maven.plugins</groupId>
              <artifactId>maven-compiler-plugin</artifactId>
              <version>3.8.1</version>
              <configuration>
                 <source>1.8</source>
                  <target>1.8</target>
              </configuration>
          </plugin>
        </plugins>
    </build>


</project>

Versioning:
============
0.0.1 |2.4.2.5
majorv.minorv.pathv | majorv.minorv.pathv.incrmentalv

Maven Commands:
================
1 mvn clean
2 mvn test
3 mvn install
4 mvn build
5 mvn deploy    

 Automation-6:
 ===============
                              ------- Jar
                   (Pom.xml) |
Java ---->Maven--->Target----|
             |                 ----- Binary
             |
             | 

   mvn clean install---- binary---- curl -x put -v username: password -t k8.jar "url of jfrog"
                                            get 
                                            post
                                            delete
x: request
u: username
t: target
k8: kubernetes

ex:https://github.com/praveen1994dec/Java_app_3.0/blob/main/Jenkinsfile

=====
@Library('my-shared-library') _

pipeline{

    agent any
    //agent { label 'Demo' }

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
        string(name: 'ImageName', description: "name of the docker build", defaultValue: 'javapp')
        string(name: 'ImageTag', description: "tag of the docker build", defaultValue: 'v1')
        string(name: 'DockerHubUser', description: "name of the Application", defaultValue: 'praveensingam1994')
    }

    stages{
         
        stage('Git Checkout'){
                    when { expression {  params.action == 'create' } }
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/praveen1994dec/Java_app_3.0.git"
            )
            }
        }
         stage('Unit Test maven'){
         
         when { expression {  params.action == 'create' } }

            steps{
               script{
                   
                   mvnTest()
               }
            }
        }
         stage('Integration Test maven'){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   mvnIntegrationTest()
               }
            }
        }
        stage('Static code analysis: Sonarqube'){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   def SonarQubecredentialsId = 'sonarqube-api'
                   statiCodeAnalysis(SonarQubecredentialsId)
               }
            }
       }
       stage('Quality Gate Status Check : Sonarqube'){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   def SonarQubecredentialsId = 'sonarqube-api'
                   QualityGateStatus(SonarQubecredentialsId)
               }
            }
       }
        stage('Maven Build : maven'){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   mvnBuild()
               }
            }
        }
        stage('Docker Image Build'){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   dockerBuild("${params.ImageName}","${params.ImageTag}","${params.DockerHubUser}")
               }
            }
        }
         stage('Docker Image Scan: trivy '){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   dockerImageScan("${params.ImageName}","${params.ImageTag}","${params.DockerHubUser}")
               }
            }
        }
        stage('Docker Image Push : DockerHub '){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   dockerImagePush("${params.ImageName}","${params.ImageTag}","${params.DockerHubUser}")
               }
            }
        }   
        stage('Docker Image Cleanup : DockerHub '){
         when { expression {  params.action == 'create' } }
            steps{
               script{
                   
                   dockerImageCleanup("${params.ImageName}","${params.ImageTag}","${params.DockerHubUser}")
               }
            }
        }      
    }
}



Advantages:
================
1. faster delivery
2. quick deployments
3. less chances of errors
4. stability
5. reliability
6. quick big fixed
7. Version controll
8. Automation

***
Java_app_3.0/Jenkinsfile Latest---- Child library
@Library('my-shared-library') _------- Parent library
****

Assignment-1  Write the groovy code to send jarfile to jfrog repo
Assignment -2 Different jenkins file scenarios



Jenkins Server installation:
========================================
  |              |
ubuntu         centos 
-------        ---------

1.yum/apt
2.packages
3.rpm packages- red hat package manager
4.docker images/container
5.curl / linux commands
6.k8 pods

Automations with jenkins
==============================

1. Write a shell script to install the jenkins on linxu server
2. Write a groovy script where the two jobs are dependent of each other

3.Write a jenkinsfile where the onestage variables are passed to other stage by using rest api automation script

To pass variables from one stage to another using REST API calls in a Jenkins pipeline, the general idea is:

Stage 1: Make a REST API call to fetch some data or variables.
Store the Response: The response from the API call is stored in environment variables.
Stage 2: Use these stored environment variables to trigger another API call or perform actions based on the fetched data.
Example Jenkinsfile
groovy

pipeline {
    agent any
    
    environment {
        // Define environment variables to store API responses or data
        API_RESULT = ''
        API_SECOND_RESULT = ''
    }

    stages {
        stage('Fetch Data from API') {
            steps {
                script {
                    // Perform a REST API call to fetch some data
                    def response = httpRequest(
                        url: 'https://api.example.com/getData',  // Replace with your actual API endpoint
                        httpMode: 'GET',
                        contentType: 'APPLICATION_JSON'
                    )
                    
                    // Parse the JSON response
                    def jsonResponse = readJSON(text: response)
                    
                    // Extract the relevant data and store it in the environment variable
                    env.API_RESULT = jsonResponse.data  // Store fetched data in environment variable
                    
                    // Debug: Output the fetched data
                    echo "Fetched data: ${env.API_RESULT}"
                }
            }
        }
        
        stage('Use Fetched Data in Second API Call') {
            steps {
                script {
                    // Use the variable from the previous stage (API_RESULT)
                    echo "Using fetched data: ${env.API_RESULT}"
                    
                    // Example of passing the fetched data into the URL for another API call
                    def secondResponse = httpRequest(
                        url: "https://api.example.com/submitData?value=${env.API_RESULT}",  // Pass the value as query parameter
                        httpMode: 'POST',
                        contentType: 'APPLICATION_JSON'
                    )
                    
                    // Parse the second API response
                    def secondJsonResponse = readJSON(text: secondResponse)
                    
                    // Store the result from the second API call
                    env.API_SECOND_RESULT = secondJsonResponse.status  // Assume response has a 'status' field
                    
                    // Output for debugging
                    echo "Second API result: ${env.API_SECOND_RESULT}"
                }
            }
        }
        
        stage('Final Decision Based on Second API Call') {
            steps {
                script {
                    // Make a decision based on the second API result
                    if (env.API_SECOND_RESULT == 'success') {
                        echo "The second API call was successful. Proceeding with further actions."
                        // Continue with further steps here if necessary
                    } else {
                        echo "The second API call failed. Stopping the pipeline."
                        currentBuild.result = 'FAILURE'
                        error("Second API call failed, stopping pipeline.")
                    }
                }
            }
        }
    }

    post {
        always {
            // This section will always execute, regardless of success or failure
            echo "Pipeline execution completed."
        }
    }
}
Explanation:
Stage 1: Fetch Data from API:

In this stage, the httpRequest step is used to make a GET request to the first API (https://api.example.com/getData).
The API response is expected to be in JSON format. Using readJSON, the response is parsed, and the value of jsonResponse.data is stored in the environment variable API_RESULT.
Stage 2: Use Fetched Data in Second API Call:

In this stage, the value stored in API_RESULT is used in another API call. Specifically, the value is passed as a query parameter in the URL (https://api.example.com/submitData?value=${env.API_RESULT}).
This second API call is a POST request, and the response is parsed into secondJsonResponse. The result of the call is stored in the API_SECOND_RESULT environment variable.
Stage 3: Final Decision Based on Second API Call:

Based on the result stored in API_SECOND_RESULT, the pipeline makes a decision. If the API returns success, it proceeds; otherwise, it fails the pipeline using error().
Post Block:

The post block is used for cleanup or finishing tasks. It runs after the stages are completed, regardless of whether the pipeline succeeded or failed.
Key Points:
Environment Variables: We store the API results in environment variables (env.API_RESULT and env.API_SECOND_RESULT) to pass data between stages.
API Calls: The httpRequest step is used for making API calls in Jenkins pipelines. Ensure that the HTTP Request Plugin is installed in Jenkins.
Dynamic Data Handling: The data fetched from the first API (API_RESULT) is dynamically used in the second API call, showing how variables can be passed between stages.
Prerequisites:
HTTP Request Plugin: Install the HTTP Request Plugin in Jenkins to use httpRequest.
API Endpoints: Replace the example API endpoints (https://api.example.com/getData and https://api.example.com/submitData) with your actual API endpoints.
API Response Structure: Modify the parsing of the API response according to your actual API response structure. The example assumes a JSON structure with fields like data and status.
By using this approach, you can efficiently pass data between stages using REST API calls in



2nd way:
=========

pipeline {
    agent any
    environment {
        API_URL = 'https://api.example.com/get-variable'  // REST API endpoint
        API_KEY = 'your-api-key-here'  // API key for authorization
        MY_VAR = ''  // This variable will store the value fetched from the API
    }

    stages {
        stage('Get variable from REST API') {
            steps {
                script {
                    // Fetch a value from the REST API using curl
                    echo "Fetching variable from API..."

                    // Use curl command to fetch the value and assign it to MY_VAR
                    sh '''
                        RESPONSE=$(curl -s -X GET "$API_URL" -H "Authorization: Bearer $API_KEY")
                        MY_VAR=$(echo $RESPONSE | jq -r '.data')  # Assuming the response has a "data" field
                        echo "Fetched value: $MY_VAR"
                    '''
                    
                    // Set the fetched value to the environment variable MY_VAR
                    env.MY_VAR = sh(script: 'echo $MY_VAR', returnStdout: true).trim()

                    // For debugging, print the value of MY_VAR
                    echo "The value of MY_VAR is: ${env.MY_VAR}"
                }
            }
        }

        stage('Use variable in next stage') {
            steps {
                script {
                    // Use the value of MY_VAR in the next stage
                    echo "Using fetched variable in the next stage: ${env.MY_VAR}"

                    // Example API call using the MY_VAR in another API request
                    def secondApiUrl = "https://api.example.com/submit-variable"
                    def secondApiResponse = sh(script: """
                        curl -s -X POST "$secondApiUrl" -H "Content-Type: application/json" \
                        -d '{"value": "${env.MY_VAR}"}'
                    """, returnStdout: true).trim()

                    // Print the response from the second API
                    echo "Second API response: ${secondApiResponse}"

                    // You can also parse and handle the second API response here
                }
            }
        }

        stage('Final Decision Based on Response') {
            steps {
                script {
                    // Final decision based on the second API response or variable value
                    if (env.MY_VAR == 'expectedValue') {
                        echo "The variable matches the expected value. Proceeding with further actions."
                    } else {
                        echo "The variable does not match the expected value. Stopping the pipeline."
                        currentBuild.result = 'FAILURE'
                        error("The variable did not match the expected value.")
                    }
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline execution completed."
        }
    }
}

Jenkins rest api 
=====================
*****Note jenkins rest api documentation URL below:
https://www.jenkins.io/doc/book/using/remote-access-api/

basic syntax
===============
https://<JENKINS_HOST>/job/MY_JOB/api/json?fetchALLbuildDetails=True

Master Slave Architecture:
==============================
                       -------- slave/agent/node
                      |
                      |
Master ---------------| (jarfile)
                       -------- slave/agent/node
(Jenkins)



***Project1:******
=============================
1.Jenkins server
2.ubuntu
3.t2.medium
4.storage - 25gb
5.launch instance
6.sudo su
7. 

sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.13" 2024-10-15
OpenJDK Runtime Environment (build 17.0.13+11-Debian-2)
OpenJDK 64-Bit Server VM (build 17.0.13+11-Debian-2, mixed mode, sharing)

8.
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

9. security -->security groups----> edit inbound rules--> type- all traffice && source anywhere IPV4
10. to get password- cat /var/lib/jenkins/....
11. install suggested pluggins
12. create first admin user ----save and continue
13. Create a pipeline jobs
    --click on new item---->pipeline---> pipelinescript from SCM--->GIT--->git repository url--->*/main -->scriptpath-Jenkinsfile
14. Add the plugins
     Dashboard-->managejenkins-->plugins--> available plugins

15. Plugins for Sonar/Jfrog -
     Sonar Gerrit
     SonarQube Scanner
     SonarQube Generic Coverage
     SonarQube Quality Gates
     Quality Gates
     Artifactory
     Jfrog

16. For any issue you can check this path--cd /var/lib/jenkins/

17. Go to mange jenkins----configure system-- global pipeline library (global trusted pipeline  libraries

    Name-my-shared-library
    Default-versionmain
    git-https://github.com/praveen1994dec/jenkins_shared_lib.git
    save and apply

18. Build
19. cd /var/lib/jenkins/
    ls -lhtr
    cd workspace/
    cd Demobatch10(job)

20. sudo apt update-y
    sudo apt install maven -y
    mvn -version
21 build with parameters
      -action--create
      -dockerhubuser- praveensingam1994
22. cd /var/lib/jenkins/workspace/Demobatch10/
    ls -lhtr
    cd target 
    (....).jar file 



                                        Docker
==============================================================================================================


Jar file
---------------
|       |      |
ubuntu  centos  fedora

Jar file disadvantages
===========================
1. Different environments in  linux systems/linux system dependecies
2. consumes cpu and memory of entire linux systems
3. systems security and reliability 
4. network maintenance 
5. linux system costing due to multiple deployments

Advantage of docker
----------------------
6. Shipment of code from one place to another place will be easyy


Docker Architecture:
=====================
                                                                         (Linux system)
                                                                        ------------------- 
                                                                       |                   |
Code----->jar--------------->|Image|--------------------------------- >| Docker-Container  |-------
----      ---- (dockerfile)       ^                                    |-------------------|
10gb      10mb       |            |                                              |
            |        |            |                                              |
            |       (source       |                                              |
            |       destination   |                                              |
            |       label           --------<---------------<-------             |
            |       from                                        |                |
            |       details                                     |                |
            |       tags)                                       |                |
            |          |                                        ^             (Path)
   ( Path)-Targat-jar--|                                        |            ---/opt       
                       |                                        |
        ---------------------------------------------------------
        |                                                       |
        |                                                       | 
-----------------------------------------              -----------------------------------------
|                                        |             |                                        |
|  FROM< >                               |             |  SOURCE< >                             |
|                                        |             |                                        | 
|  MAINTAINER< > (whoismaintain doc file)|             |                                        |
|  ENV < >                               |             |                                        |       
|  ARGS< >                               |             |                                        | 
|  RUN< > (Installing all soft/binaries  |             |                                        |
|  COPY< >                               |             |                                        | 
|  EXPOSE<PORT>                          |             |                                        | 
|  ENTRYPOINT< >                         |             |                                        |
|  volume /map target                    |             |                                        |
|                                        |             |                                        |
------------------------------------------             ------------------------------------------

|---------------------------------------------------|
|ADD                           |          COPY      |
|----------------------------- |--------------------|
|it will unzip                 |  Copy the jar from |
|any .zip files automatically  |  lap to container  |
| and copy in container        |                    |
-----------------------------------------------------
|    CMD                       | ENTRIPOINT         |
-----------------------------------------------------
|  The values can be ovverriden| Some command tostart| 
|                              | the jar file        |
|                              |                     |
|                              |                     |
----------------------------------------------------------


Example docker file:
---------------------
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY ./target/*.jar /app.jar
CMD ["java", "-jar", "/app.jar"]


 Multistage docker file:
---------------------------------

#Stage 1
# initiazlize build and set base image for first stage

FROM maven:3.6.3-adoptopenjdk-11 as stage1

#speed up Maven JVM a bit
ENV MAVEN_OPTS="-XX:+TieredCompilation -XX:TieredStopAtLevel=1"
# set working directory
WORKDIR /opt/demo
# copy just pom.xml
COPY pom.xml
#go-ffiline using the pom.xml
RUN mvn dependency:go-offline
#copy your other files
COPY ./src ./src

# compile the source code and package it in a jar file

RUN mvn clean install -Dmaven.test.skip=true

#Stage2

#set base image for second stage
FROM adoptopnjdk/openjdk111:jre-11.0.9_11-alpine

#set deployment directory
WORKDIR /opt/demo

#copy over the built artifact from the maven image
COPY --from=stage1 /opt/demo/taget/demo.jar /opt/demo

Docker containers
---------------------
1.list of running  containers- docker ps 
2.list of all containers - docker ps -a
3. To enter into the container - docker exec -it c39b83a46949 /bin/sh
4. To star the container- docker start c39b83a46949
5. To find the complete skeleton json of container- docker inspect c39b83a46949
6. To stop the container - docker stop c39b83a46949
7. docker network ls

3 types of docker network
---------------------------
1. bridge
2. overlay
3. host


##Install in Amazon Ubuntu
#!/bin/bash
sudo apt update -y

sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" -y

sudo apt update -y

apt-cache policy docker-ce -y

sudo apt install docker-ce -y

#sudo systemctl status docker

sudo chmod 777 /var/run/docker.sock

##Install in Amazon Ubuntu
sudo usermod -aG docker $USER
docker pull docker.bintray.io/jfrog/artifactory-oss:latest
sudo mkdir -p /jfrog/artifactory
sudo chown -R 1030 /jfrog/
docker run --name artifactory -d -p 8081:8081 -p 8082:8082 -v /jfrog/artifactory:/var/opt/jfrog/artifactory docker.bintray.io/jfrog/artifactory-oss:latest

Disadvantages of dockercompose
---------------------------
1. No security
2. Multi arhitecture format
3.Maintenance of docker containers
4. No dashboard
5. No proper rollback
6. No proper deployment strategy

                                Kubernetes K8 
==============================================================================================================

Architecture of Kubernetes
----------------------------------
yaml
|
|
 --
   |
   | 
   |--> Master                                                 Slave/Node
 ------------------------                                    ----------------
 |               
 |->     API SERVER------>>---------->>---------->>------------->>cublet(agent)
           ^                                                      PODS  -- POD
           |                                                            -- DEPLOYMENT
           |                                                            -- SERVICE
           |                                                            --  CUSTOME RESOURCE DEFINITION
           |                                                            --  INGRESS
           |                                                            --   RBAC
           |                                                            --   Network.io
           |                                                            --  Storage.io
           |                                                            --  Replica set
           |                                                            --   config map
           |                                                            --   statefullset
           ^                                                            --   persistent volumes
           |                                                            --  Daemon set
           |                                                            --   secrets
 |->    ETCD (It stores all the data in kub)                       Proxy
 |        ^  (d means distributed database)                        Continer d or Container Runtime
 |        |  (it stores the data in key: value format)
 |-->     Control Manager   < ---------------------|
 |     CPU                                         |
 |    - Node controller                            |  
 |    -Replication controller                      |
 |    - Network controller                         |
 |-->    Scheduler---------------------------------


 States of POD:
------------------------
-----> Troubleshooting of K8
  | -->   Running---- sucess state
  | -->   Crashloopback-- any issues in appplication
  | -->   Pending--- if pos is not able to get data
  | -->  restart-----if any issue in container
  | -->   exit------ pod never ran
  | -->  imageback pull off-- if image is not downloaded
  | -->  out of memory state-- if pod is not given sufficent CPU/ememory
  | --> evicted state-- inbetween state (before exit/ pending)
      


Kubernetes file( Yaml) Manifest file
-------------------------------------
-- Api version ----> apps/v1
                    v1
                    network.io/v1
                    storage.io/v1
                    rback                   
                    service.io/v1                                           
-- Kind -----POD/Service/ingress-
-- Metadata--
         labels
         annotations

-- Spec

Kuberntes manifest file for pod
=================================
Ex:
----
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx-container
    image: nginx:latest
    ports:
    - containerPort: 80

kubernetes manifest file for service
=========================================
ex:
---
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
  labels:
    app: nginx
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: ClusterIP

Service:
----------
- Cluster IP
- Node Port
- loadbalancer
- Cname (Cannonical name)


kubernetes manifest file for replicaset
==========================================
ex:
----
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replicaset
  labels:
    app: nginx
spec:
  replicas: 3  # Desired number of Pods
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx:latest
          ports:
            - containerPort: 80


kubernetes manifest file for deployment
===========================================
Ex:
----

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3  # Number of replicas (Pods) to run
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx:latest
          ports:
            - containerPort: 80


Project 2:
=----------
1. Amazon linux
2. Amazon linux 2 AMI
3. T2.medium
4. 20 gb
5. sudo su
6. yum update -y
7. yum install docker -y
8. systemctl start docker
9. systemctl enable docker
10. yum install conntrack -y
11. curl -LO https://storage.googleapis.com/minikube/releas/latest/minikube-linux-amd64
12. sudo install  minikube-linux-amd64 /usr/local/bin/minikube
13. star your minikube 
    /usr/local/bin/minikube start --force --driver=docker
14. cd /opt
Install maven
15. wget https//
 or
15. yum install maven -y
16. yum install git -y
17. yum install java -y

19.Continue u the project from documentations




       Native(Core) Kubernetes objects
|---------------------------------------------------------|
|                                                         |                        
|                                                         |                   
|                                                         |
|                                                         |
|                                                         | 
| POD                Node                 Serivce         |
|                                                         |
|                                                         |
|                                                         |
|                                                         |
|                                                         |
|-------------------------------------------------------- |



      Custom Resource object definition CRD
|---------------------------------------------------------|
|                                                         |                        
|                                                         |                   
|                                                         |
|                                                         |
|                                                         | 
|     Log                                  Alert          |
|                                                         |
|                                                         |
|                                                         |
|                                                         |
|                                                         |
|-------------------------------------------------------- |

API Version   /apis/group/version

Groups                       Version
apps                           v1
authetication.k8s.io           v1,v1batak,v1alpha1
authorization.k8s.io           v1

certificates.k8s.io            v1.v1alpha1


networking.k8s.io               v1.1alpha1
node.k8s.io                     v1

rbac.authorization.k8s.io       v1

scheduling.k8s.io                v1
storage.k8s.io                   v1



kubectl get pods 


kubectl delete pods 







Custom_Resource_DefinitioN
================================

apiVersion: apiextensions.k8s.io/v1
kind: CustomResourceDefinition
metadata:
 # name must match the spec fields below, and be in the form: <plural>.<group>
 name: myplatforms.contoso.com
spec:
 # group name to use for REST API: /apis/<group>/<version>
 group: contoso.com
 names:
   # plural name to be used in the URL: /apis/<group>/<version>/<plural>
   plural: myplatforms
   # singular name to be used as an alias on the CLI and for display
   singular: myplatform
   # kind is normally the CamelCased singular type. Your resource manifests use this.
   kind: MyPlatform
   # shortNames allow shorter string to match your resource on the CLI
   shortNames:
   - myp
 # either Namespaced or Cluster
 scope: Namespaced
 versions:
   - name: v1alpha1
     # Each version can be enabled/disabled by Served flag.
     served: true
     # One and only one version must be marked as the storage version.
     storage: true
     schema:
       openAPIV3Schema:
         type: object
         properties:
           spec:
             type: object
             properties:
               appId:
                 type: string
               language:
                 type: string
                 enum:
                 - csharp
                 - python
                 - go
               os:
                 type: string
                 enum:
                 - windows
                 - linux
               instanceSize:
                 type: string
                 enum:
                   - small
                   - medium
                   - large
               environmentType:
                 type: string
                 enum:
                 - dev
                 - test
                 - prod
               replicas:
                 type: integer
                 minimum: 1
             required: ["appId", "language", "environmentType"]
         required: ["spec"]
-------------------------------

apiVersion: contoso.com/v1alpha1
kind: MyPlatform
metadata:
 name: test-dotnet-app
spec:
 appId: testdotnetapp
 language: csharp
 os: linux
 instanceSize: small
 environmentType: dev
 replicas: 3



                                Python
=============================================================================================================

   |         |    |              |   |         |              |           |               |                      |         |    |              |   |         |              |           |               | 
   |         |    |              |   |         |              |           |               |
Shellscript  |    |        buildtool |  Toconnectwithanycloud |  modules/libraries   datamanipulation      replaceshellscript                                   dataengineeringtoconnectDB's 
                  |                  |
                RestAPI            security/monitoring/deployement



Jenkins         Docker     K8     Python
  |              |          |       |
Envvariables    Args      metada  variables
parameters      Env



Python Variables:
--------------------

variable = datatype

1.a="test"(String variable)
2.c=1.1(float variable)
3.d=1 (integer)

4.["jeans", "shirt"     ] == list data type

list[0] - jeans
list[1] -shirt


5. dictionary ={"emmaculate": "clean,"clostrofobia" }- no duplicates, mutable/changeble

6. tuple  - non mutable


Python modules/libraries
--------------------------------
                    import(module)
                         |
----------------------------------------------------------------------------------------------------
|        |       |              |        |         |    |    |       |       |      |           |
OS      json     request=curl   BOT03    datetime math  ssh  docker  parmiko |      subprocess  flask/dgango
|                 (req API)                                                  |
|                   |                                                       pgintx/pytex
 --------------     |
 |             |    |
folders  os details |
                    |
         ------------------------
           |    |     |     |
           GET PUT  DELETE POST



import os
import request
import json

list1= ["oil", "milk", "tea"]

(Intendenation)--->def manipulate()



1 Login building:
-----------------
Step1: hit the rest endpoint in the github
Step2: Fetch all  the branches data from a repo
Step3: if that list of branches does not have heydevops branchg then create a new branch
Step4: copy/clone the code to new branch
Step5: push the code to new branch
Step6: validate the branch presence in github


Loops and condtions
------------------------
 for /while (two loops are used majorly in python
 if/else (conditional block of code in python

psedo code:
if("branch"=="heydevops")
  create branch= request.post "url .header {username,data}


Pythone OPT Verfication code:
---------------------------------
import os
import math
import random



digits="0123456789"
OTP=""
#Six digit password
for i in range(6):
    OTP+=digits[math.floor(random.random()*10)]
otp = OTP + " is your OTP"
msg= otp

print(msg)





{
  "people": [
    {
      "craft": "ISS",
      "name": "Oleg Kononenko"
    },
    {
      "craft": "ISS",
      "name": "Nikolai Chub"
    },
    {
      "craft": "ISS",
      "name": "Tracy Caldwell Dyson"
    },
    {
      "craft": "ISS",
      "name": "Matthew Dominick"
    },
    {
      "craft": "ISS",
      "name": "Michael Barratt"
    },
    {
      "craft": "ISS",
      "name": "Jeanette Epps"
    },
    {
      "craft": "ISS",
      "name": "Alexander Grebenkin"
    },
    {
      "craft": "ISS",
      "name": "Butch Wilmore"
    },
    {
      "craft": "ISS",
      "name": "Sunita Williams"
    },
    {
      "craft": "Tiangong",
      "name": "Li Guangsu"
    },
    {
      "craft": "Tiangong",
      "name": "Li Cong"
    },
    {
      "craft": "Tiangong",
      "name": "Ye Guangfu"
    }
  ],
  "number": 12,
  "message": "success"
}

import json
import requests
person_ISS=[]
person_Tiangong=[]
def space_data(url):
    data = requests.get(url)
   # print(data.json())
    dump = data.json()
    for person in dump["people"]:
        print(person["craft"])
        if (person["craft"] == "ISS"):
            person_ISS.append(person["name"])
        else:
            person_Tiangong.append(person["name"])
    
    
    print("Total number of persons in ISS" + str(len(person_ISS)))
    print("Total number of persons in ISS" + str(len(person_Tiangong)))

space_data("http://api.open-notify.org/astros.json")

OOPS Concepts - Ojbect oriented programing language
--------------------------------------------------------

####CREATE AN OBJECT
class Tools:
    car_list=[]
    name = "Jenkins"
    version = 20
    date = "20/11"
    cartyres=4
    car_name="toyota"

    def cartyres1(self):
        if self.cartyres==4:
            self.car_list.append(self.car_name)
            print(self.car_list)
        else:
            print("Only two wheelers are there")

Toyota = Tools()
Toyota.cartyres1()


1.write a python code to extract the github branches and manipulate the data
-----------------------------------------------------------------------------------------------



To extract GitHub branches and manipulate the data using Python, you'll need to interact with GitHub's API. Here's a basic example using Python's requests library to fetch the branches of a GitHub repository, then manipulate or process that data.

In this example, we'll:

Use the GitHub API to get the list of branches from a repository.
Manipulate the data (like filtering branches, counting them, etc.).
Display the results.
Requirements:
requests: To make HTTP requests to the GitHub API.
Install it via pip if you haven't already:
bash

pip install requests
Python Code to Extract GitHub Branches and Manipulate Data:
python

import requests
import json

# GitHub API endpoint to get branches
GITHUB_API_URL = "https://api.github.com/repos/{owner}/{repo}/branches"
GITHUB_TOKEN = "your_github_token"  # Replace with your GitHub Personal Access Token (PAT)

# Function to get branches from the GitHub repository
def get_github_branches(owner, repo):
    url = GITHUB_API_URL.format(owner=owner, repo=repo)
    headers = {'Authorization': f'token {GITHUB_TOKEN}'}

    # Make the GET request to fetch branches
    response = requests.get(url, headers=headers)
    
    if response.status_code == 200:
        branches = response.json()  # Parse the JSON response
        return branches
    else:
        print(f"Failed to retrieve branches: {response.status_code}")
        return []

# Function to filter branches (example: filter branches starting with 'dev')
def filter_branches_by_prefix(branches, prefix):
    filtered_branches = [branch['name'] for branch in branches if branch['name'].startswith(prefix)]
    return filtered_branches

# Function to count branches
def count_branches(branches):
    return len(branches)

# Function to print branch names
def print_branch_names(branches):
    print("Branches:")
    for branch in branches:
        print(branch['name'])

def main():
    owner = "your_github_username_or_organization"  # Replace with the GitHub repository owner (username or org)
    repo = "your_repo_name"  # Replace with the GitHub repository name
    
    # Step 1: Get branches from the GitHub repository
    branches = get_github_branches(owner, repo)
    
    if branches:
        # Step 2: Print all branch names
        print_branch_names(branches)
        
        # Step 3: Count total branches
        total_branches = count_branches(branches)
        print(f"\nTotal branches: {total_branches}")
        
        # Step 4: Filter branches that start with 'dev' (as an example)
        dev_branches = filter_branches_by_prefix(branches, "dev")
        print(f"\nBranches that start with 'dev': {dev_branches}")
    else:
        print("No branches to display.")

if __name__ == "__main__":
    main()
Explanation:
Fetching branches:

The get_github_branches() function sends a GET request to the GitHub API endpoint for fetching the branches of a repository.
It expects the owner (username or organization name) and the repo (repository name) as parameters.
The response is parsed as JSON, and the function returns the list of branches.
Filtering branches:

In filter_branches_by_prefix(), branches are filtered based on their names, using the startswith() method. In this case, we're filtering branches whose names start with 'dev'.
Counting branches:

The count_branches() function simply returns the length of the list of branches.
Displaying the results:

The print_branch_names() function iterates through the list of branches and prints their names.
In the main() function, we use the other functions to extract, manipulate, and display the branch data.
Sample Output:
bash

Branches:
main
dev-branch
feature/xyz
dev-xyz
release/v1

Total branches: 5

Branches that start with 'dev': ['dev-branch', 'dev-xyz']
Important Notes:
GitHub Personal Access Token (PAT): For accessing private repositories or if you hit rate limits with the public API, you will need to generate a GitHub Personal Access Token (PAT) with the appropriate permissions. To generate a token:

Go to GitHub > Settings > Developer Settings > Personal Access Tokens.
Select the necessary permissions (e.g., repo for full control over private repositories).
Copy the token and use it in your code as shown above.
Rate Limiting: GitHub API has rate limits. With authentication (using a PAT), you get a higher limit. You can check the current rate limit with:

python

response = requests.get("https://api.github.com/rate_limit", headers={'Authorization': f'token {GITHUB_TOKEN}'})
print(response.json())
Error Handling: You can improve error handling by checking for different types of API errors (e.g., invalid token, 404 for non-existing repositories, etc.).

Customization:
You can further customize the manipulation logic depending on your use case, such as sorting branches, grouping by patterns, or even updating branches. You can also integrate this with other actions like creating or deleting branches via the GitHub API.




import mysql.connector
# Establish the MySQL database connection
def connect_to_mysql(host, user, password, database):
    try:
        connection = mysql.connector.connect(
            host=host,
            user=user,
            password=password,
            database=database
        )
        print("Connection established successfully.")
        return connection
    except mysql.connector.Error as err:
        print(f"Error: {err}")
        return None

# Function to fetch data from a table
def fetch_data_from_table(connection, query):
    cursor = connection.cursor(dictionary=True)  # Using dictionary cursor for easier access to columns by name
    try:
        cursor.execute(query)
        result = cursor.fetchall()  # Fetch all rows
        return result
    except mysql.connector.Error as err:
        print(f"Error: {err}")
        return None
    finally:
        cursor.close()

# Function to sort the data (by a specific column)
def sort_data(data, sort_by_column):
    # Sort the data based on the column name (e.g., 'age')
    return sorted(data, key=lambda x: x[sort_by_column])

# Main function to run the process
def main():
    # MySQL connection parameters
    host = 'localhost'  # Change this to your MySQL host
    user = 'root'  # Change this to your MySQL username
    password = 'yourpassword'  # Change this to your MySQL password
    database = 'yourdatabase'  # Change this to your MySQL database name

    # Connect to MySQL database
    connection = connect_to_mysql(host, user, password, database)

    if connection:
        # Example query to get data from a table (change 'your_table' to your actual table name)
        query = "SELECT * FROM your_table"

        # Fetch the data
        data = fetch_data_from_table(connection, query)

        if data:
            print("Original Data:")
            for row in data:
                print(row)

            # Sort the data by a specific column, e.g., 'age' or 'name'
            sorted_data = sort_data(data, 'your_column_to_sort_by')  # Replace with actual column name

            print("\nSorted Data:")
            for row in sorted_data:
                print(row)
        
        # Close the connection
        connection.close()

# Run the main function
if __name__ == "__main__":
    main()




2. write a python code for hitting the mysqldatabase  and get the data and extract the data.
-----------------------------------------------------------------------------------------------

To interact with a MySQL database in Python, you typically use a library like mysql-connector-python or PyMySQL. Below is a simple Python script that connects to a MySQL database, fetches data, and extracts the results.

Requirements:
MySQL Connector: You can install the MySQL connector for Python via pip:

bash

pip install mysql-connector-python
Database Setup: Ensure you have a MySQL server running, and you know the following information:

Host (e.g., localhost or IP address of the server)
Database name
Username
Password
Python Code Example:
python

import mysql.connector
from mysql.connector import Error

# Function to connect to the MySQL database and extract data
def fetch_data_from_mysql(host, database, user, password):
    try:
        # Establish connection to the MySQL server
        connection = mysql.connector.connect(
            host=host,
            database=database,
            user=user,
            password=password
        )

        if connection.is_connected():
            print("Successfully connected to the database")
            
            # Create a cursor object using the connection
            cursor = connection.cursor(dictionary=True)
            
            # SQL query to fetch data from a table (modify the table name as needed)
            query = "SELECT * FROM your_table_name"  # Replace 'your_table_name' with your actual table name
            cursor.execute(query)
            
            # Fetch all rows from the executed query
            rows = cursor.fetchall()
            
            # Extract and print the data
            for row in rows:
                print(row)  # Each row is a dictionary with column names as keys
            
    except Error as e:
        print(f"Error: {e}")
    finally:
        # Close the cursor and connection
        if connection.is_connected():
            cursor.close()
            connection.close()
            print("MySQL connection closed")

# Replace with your MySQL server details
host = "localhost"          # or IP address
database = "your_database"  # Replace with your database name
user = "your_username"      # Replace with your MySQL username
password = "your_password"  # Replace with your MySQL password

# Fetch data from MySQL database
fetch_data_from_mysql(host, database, user, password)
Explanation:
Establish Connection:

We connect to the MySQL database using mysql.connector.connect(). You need to provide the host, database name, username, and password.
Cursor Creation:

We create a cursor object using connection.cursor(). This cursor is used to execute SQL queries.
Executing Query:

The query "SELECT * FROM your_table_name" retrieves all rows from the specified table. Modify the table name and SQL query as per your requirement.
Fetching Data:

The cursor.fetchall() method fetches all rows of the query result. The result is a list of dictionaries, where each dictionary represents a row with column names as keys.
Closing the Connection:

After executing the queries, it's a good practice to close the cursor and connection using cursor.close() and connection.close().
Sample Output:
Assuming your table has columns id, name, and age, the output might look like:

python

Successfully connected to the database
{'id': 1, 'name': 'Alice', 'age': 30}
{'id': 2, 'name': 'Bob', 'age': 25}
{'id': 3, 'name': 'Charlie', 'age': 35}
MySQL connection closed
Error Handling:
The try-except block ensures that any connection issues or query errors are caught and reported. For instance, if the database credentials are wrong or the table doesn't exist, an error message will be shown.

Customization:
SQL Queries: You can modify the query variable to fetch specific columns or apply filters (e.g., SELECT id, name FROM your_table_name WHERE age > 30).
Insert/Update/Delete: You can also perform other operations (INSERT, UPDATE, DELETE) using cursor.execute() by changing the SQL query type.
Let me know if you need help with anything else!




3. Write the python code to fetch the data from kubernetes and put the data in csv file and extract the data from  csv file
-----------------------------------------------------------------------------------------------

To fetch data from a Kubernetes cluster and store it in a CSV file, we'll use the Python Kubernetes client (kubernetes library) to interact with the Kubernetes API, extract data, and then save it into a CSV file.

Steps:
Install the required libraries:

Kubernetes client: To interact with the Kubernetes API.
CSV: To handle CSV file operations.
Install the required libraries using pip:

bash

pip install kubernetes pandas
Python Code:

First, we will fetch data from the Kubernetes API (e.g., pod information).
Then, we'll write that data to a CSV file.
Finally, we'll read the data from the CSV file.
Python Code Example:
python

import csv
import pandas as pd
from kubernetes import client, config
from kubernetes.client.rest import ApiException

# Function to fetch pods data from Kubernetes cluster
def fetch_pods_data():
    # Load Kubernetes config from default location (~/.kube/config)
    try:
        config.load_kube_config()  # If you're running outside the cluster
        # config.load_incluster_config()  # Uncomment this if you're running inside the cluster

        # Create API client
        v1 = client.CoreV1Api()

        # Get pods in the default namespace (change if necessary)
        pods = v1.list_pod_for_all_namespaces(watch=False)

        pods_data = []

        for pod in pods.items:
            pod_info = {
                "Name": pod.metadata.name,
                "Namespace": pod.metadata.namespace,
                "Status": pod.status.phase,
                "Node": pod.spec.node_name,
                "Creation Time": pod.metadata.creation_timestamp,
                "Labels": pod.metadata.labels
            }
            pods_data.append(pod_info)

        return pods_data

    except ApiException as e:
        print(f"An error occurred: {e}")
        return []

# Function to write data to a CSV file
def write_to_csv(data, filename="kubernetes_pods_data.csv"):
    if data:
        # Writing data to CSV
        keys = data[0].keys()
        with open(filename, mode='w', newline='') as file:
            writer = csv.DictWriter(file, fieldnames=keys)
            writer.writeheader()
            writer.writerows(data)
        print(f"Data written to {filename}")
    else:
        print("No data available to write.")

# Function to read data from the CSV file and display it
def read_from_csv(filename="kubernetes_pods_data.csv"):
    try:
        df = pd.read_csv(filename)
        print(df)
    except FileNotFoundError:
        print(f"{filename} not found.")

def main():
    # Fetch Kubernetes pod data
    pods_data = fetch_pods_data()
    
    # Write the fetched data to CSV
    write_to_csv(pods_data)

    # Read data from the CSV file and display
    read_from_csv()

if __name__ == "__main__":
    main()
Explanation:
Fetching Kubernetes Data (fetch_pods_data):

The function fetch_pods_data uses the Kubernetes Python client (kubernetes.client) to fetch pod data.
The v1.list_pod_for_all_namespaces(watch=False) method fetches all pods from all namespaces. You can adjust this if you only need data from a specific namespace.
We store relevant information (e.g., Pod Name, Namespace, Status, Node, etc.) in a list of dictionaries (pods_data).
Writing Data to CSV (write_to_csv):

We use Python's csv.DictWriter to write the fetched data into a CSV file.
The keys for the CSV file are the column names, which are taken from the keys of the first dictionary in the data list.
Reading Data from CSV (read_from_csv):

The read_from_csv function uses pandas to read the CSV file and display the data in tabular format.
Main Execution:

The main() function fetches the Kubernetes data, writes it to a CSV file, and then reads and displays the contents of that CSV file.
Output:
The CSV file (kubernetes_pods_data.csv) will look something like this:

sql

Name,Namespace,Status,Node,Creation Time,Labels
pod-1,default,Running,node1,2021-11-01T00:00:00Z,"{'app': 'web'}"
pod-2,default,Pending,node2,2021-11-01T00:05:00Z,"{'app': 'database'}"
After running the script, you will also see the output printed from the CSV file using pandas:

sql

          Name Namespace   Status   Node         Creation Time            Labels
0     pod-1  default    Running  node1   2021-11-01T00:00:00Z     {'app': 'web'}
1     pod-2  default    Pending  node2   2021-11-01T00:05:00Z  {'app': 'database'}
Notes:
Kubernetes Configuration:

If you're running the script outside the Kubernetes cluster, the config.load_kube_config() will load the configuration from your local ~/.kube/config file.
If you're running inside a Kubernetes pod, use config.load_incluster_config() instead.
Customizing the Data:

The data fetched from Kubernetes can be customized. For example, you can fetch different resources (e.g., deployments, services) or more detailed pod information by modifying the API calls accordingly.
Error Handling:

We use try-except blocks to handle potential errors such as API connection issues, missing configuration files, or non-existing CSV files.




