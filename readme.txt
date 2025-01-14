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

         
     SSL/TLS             UDP/TCP/
User----------> Request------------------> Regional server---------> DNS Server

Important networking tools for Devops Engineering
=======================================================
1.PING Command: ping google.com
=============== 
akhilpagadapoola@Akhils-MacBook-Air Jenkins % ping google.com
PING google.com (142.250.193.46): 56 data bytes
64 bytes from 142.250.193.46: icmp_seq=0 ttl=112 time=56.100 ms
64 bytes from 142.250.193.46: icmp_seq=1 ttl=112 time=53.291 ms
64 bytes from 142.250.193.46: icmp_seq=2 ttl=112 time=51.908 ms

2.Traceroute Command:  traceroute google.com 
====================
akhilpagadapoola@Akhils-MacBook-Air Jenkins % traceroute google.com 
traceroute to google.com (142.250.192.206), 64 hops max, 52 byte packets
 1  reliance.reliance (192.168.29.1)  9.278 ms  4.754 ms  4.402 ms
 2  10.14.240.1 (10.14.240.1)  9.956 ms  9.464 ms  8.910 ms
 3  172.31.2.102 (172.31.2.102)  18.370 ms
    172.31.2.120 (172.31.2.120)  21.698 ms  21.247 ms
 4  192.168.59.122 (192.168.59.122)  16.644 ms
    192.168.59.120 (192.168.59.120)  33.227 ms
    192.168.59.124 (192.168.59.124)  23.655 ms

3.Netstat Command: netstat -a
4.Nmap Command: nmap -p 1-1000 target



