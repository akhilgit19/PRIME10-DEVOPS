                                                  GIT   
                                              ==============

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


Git basic Commands:
=======================
1.git init
2.git clone
3.git pull
4.git push   
5.git commit -m "message" 
6.git status
7.git log
8.git diff
9.git config
10.git merge
11.git pull   (To get the difference of changes in the respository)
12.git checkout -b branch_name (To create a branch)
13.git add .       ( To add all the files to 
14.git cherypick
15.git fetch
16.git rebase
17.git revert
18.git switch  branch_name
19.git branch -d branch_name
20.git branch -a ( To list the branches )


Git Automation:
https://docs.github.com/en/rest/branches?apiVersion=2022-11-28
https://github.com/praveen1994dec/Knowledge_Base/blob/main/Jenkins/Jenkins%20Notes.pdf

Github rest API'S



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
                                                  ==============

         
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
                                                 ==================================


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

ex:
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



AWS instance for project
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
11.
