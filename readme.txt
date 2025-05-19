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
================================================================================

echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/akhilgit19/test.git
git push -u origin main

push an existing repository from the command line
==============================================================================

git branch -M main
git remote add origin https://github.com/akhilgit19/test.git
git push -u -f origin main



=============================
*****Git basic Commands:
=============================
1.git init <directory>-  Create empty git repo in specified directory with no argument to initialize the current 
                         directory.
  Command:- git init
  ================================================================================
2.git clone <repo>-  Clone repo located at <repo> onto local mahcine.Original repo can be located on the local 
                     filesystem.
  Command:- git clone https://github.com/akhilgit19/test.git
  ================================================================================
3.git config user.name <name>- Define author name to used for all commits in current repo.Devs commonly use -- 
                               global flag to set config options for current user.

  Command:-git config --global user.name honey
  ================================================================================
4.git add . - Stage all changes in<directory> for the next commit.

  Command: git add .
  ================================================================================
5.git commit -m "<message>"- Commit the staged snapshot, but instead of launching a text editor,use<message> as 
   the commit message.

  Command:- git commit -m "firstcommit"
  ================================================================================
6.git status - List which files are staged,unstaged, and untracked.
  Command:- git status
  ================================================================================
   akhilpagadapoola@Akhils-MacBook-Air test % git status
   On branch main
   Your branch is up to date with 'origin/main'.

   Untracked files:
     (use "git add <file>..." to include in what will be committed)
	 test.txt

    nothing added to commit but untracked files present (use "git add" to track)
    akhilpagadapoola@Akhils-MacBook-Air test %
   ================================================================================

7.git log    - Display the entire commit history using the default format.

  Command:- git log
  ================================================================================
  Ex:
  akhilpagadapoola@Akhils-MacBook-Air test % git log
  commit dacdf7bcdb534b73e38e647734e52f10c245e0cf (HEAD -> main, origin/main)
  Author: akhilgit19 <akhilpagadapoola123@gmail.com>
  Date:   Fri Feb 7 13:15:29 2025 +0530

     del pyt

  commit 061c435513dd7a44d30aa8e46daa407f90eab727
  Merge: 5b0ba80 8577b00
  Author: akhilgit19 <138980055+akhilgit19@users.noreply.github.com>
  Date:   Fri Feb 7 13:13:18 2025 +0530

     Merge pull request #1 from akhilgit19/feature
    
     feature

  commit 8577b000746cf2dc0c22933892a9ef906a2d39bb (origin/feature)
  Author: akhilgit19 <akhilpagadapoola123@gmail.com>
  Date:   Fri Feb 7 13:10:43 2025 +0530

     feature

  commit 5b0ba804bddc3d80a291a7b201dbdcee6f0d8c75
  Author: akhilgit19 <akhilpagadapoola123@gmail.com>
  :
 ================================================================================

8.git diff   - show unstaged changes between your index and working directory
 Command: git diff
 ================================================================================


=============================
*****Git Undoing Changes Commands:
=============================
9.git revert <commit>  - Create new commit that undoes all the changes made in <commit>, then apply it to the 
                       current batch
 Command:- git revert dec1576 (basically it does reverse of the that commit)
  ================================================================================
  akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
  00f6979 (HEAD -> main, origin/main) Reapply "delet py"
  dec1576 Revert "delet py"
  599fe8b delet py
  3da3305 add py
  d85160e first commit
  ================================================================================
10.git reset <file>  - Remote<file> from the staging area,but leave the working directory unchanged.This unstages a file without overwriting any changes.

 Command:- git reset test.txt 
 ===============================
  akhilpagadapoola@Akhils-MacBook-Air test % git status
  On branch main
  Your branch is up to date with 'origin/main'.

  Untracked files:
   (use "git add <file>..." to include in what will be committed)
	 test.txt

   nothing added to commit but untracked files present (use "git add" to track)
   akhilpagadapoola@Akhils-MacBook-Air test % git add test.txt
   akhilpagadapoola@Akhils-MacBook-Air test % git status
   On branch main
   Your branch is up to date with 'origin/main'.

   Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test.txt

  akhilpagadapoola@Akhils-MacBook-Air test % git reset test.txt
  akhilpagadapoola@Akhils-MacBook-Air test % git status
  On branch main
  Your branch is up to date with 'origin/main'.

  Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test.txt

  nothing added to commit but untracked files present (use "git add" to track)
  ================================================================================


11.git  clean -n - Shows which files would be removed from working directory. Use the -f flag in place of the -n 
                   flag to execute the clean
Command:-git  clean -n
=========================
akhilpagadapoola@Akhils-MacBook-Air test % git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test.txt

nothing added to commit but untracked files present (use "git add" to track)
akhilpagadapoola@Akhils-MacBook-Air test % git  clean -n
Would remove test.txt
================================================================================



==================================
*****Rewriting Git History Commands:
==================================
12.git commit --amend - Replace the last commit with the staged changes and last commit combined.Use with the 
                        nothing staged to edit the last commit's message
 Command: git commit --amend
 ==================================
 akhilpagadapoola@Akhils-MacBook-Air test % touch test7.txt
 akhilpagadapoola@Akhils-MacBook-Air test % git add .
 akhilpagadapoola@Akhils-MacBook-Air test % git commit --amend
 [main f649bd7] adding 7 txt with 5 and 6.txt
  Date: Sat Feb 8 12:03:46 2025 +0530
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.txt
 create mode 100644 test6.txt
 create mode 100644 test7.txt
 akhilpagadapoola@Akhils-MacBook-Air test %  git log --oneline 
 f649bd7 (HEAD -> main) adding 7 txt with 5 and 6.txt
 9a28ea0 test4.txt
 ac9426b created test3.txt
 fbeecd6 test2.txt
 ad53963 (origin/main) first commit
 akhilpagadapoola@Akhils-MacBook-Air test % 

================================================================================

   
13.git rebase <base>- Rebase the current branch onto<base>.<base> can be a commit ID, branch name, a tag, or a 
                      relative reference to HEAD.

   Command:-git rebase feature
   =========================
akhilpagadapoola@Akhils-MacBook-Air test % git switch main  
akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
fc2a20d (HEAD -> main) e
467494c d
81223dc c1
f77b7ab c0
akhilpagadapoola@Akhils-MacBook-Air test % git switch feature
Switched to branch 'feature'
akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
6712c2e (HEAD -> feature) c
5de56f1 b
e822356 a
81223dc c1
f77b7ab c0
akhilpagadapoola@Akhils-MacBook-Air test % git switch main   
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)
akhilpagadapoola@Akhils-MacBook-Air test % git rebase feature
Successfully rebased and updated refs/heads/main.
akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline 
ee4ef63 (HEAD -> main, feature) c
5fdcc91 b
ba6571b a
fc2a20d e
467494c d
81223dc c1
f77b7ab c0
3bec5e5 (origin/main) first commit






14.git reflog - show a log of changes to the local repository's HEAD.
                Add --relative-date flag to show date info or --all to show all refs.
  Command: git reflog:
  =======================
akhilpagadapoola@Akhils-MacBook-Air test % git reflog
f649bd7 (HEAD -> main) HEAD@{0}: commit (amend): adding 7 txt with 5 and 6.txt
56a01bc HEAD@{1}: commit (amend): test5.txt
2f588b9 (feature) HEAD@{2}: rebase (finish): returning to refs/heads/main
2f588b9 (feature) HEAD@{3}: rebase (start): checkout feature
9a28ea0 HEAD@{4}: checkout: moving from feature to main
2f588b9 (feature) HEAD@{5}: commit: test5.txt
9a28ea0 HEAD@{6}: rebase (finish): returning to refs/heads/feature
9a28ea0 HEAD@{7}: rebase (start): checkout main
ac9426b HEAD@{8}: checkout: moving from main to feature
9a28ea0 HEAD@{9}: commit: test4.txt
ac9426b HEAD@{10}: checkout: moving from feature to main
ac9426b HEAD@{11}: rebase (finish): returning to refs/heads/feature
ac9426b HEAD@{12}: rebase (start): checkout main
fbeecd6 HEAD@{13}: checkout: moving from main to feature
ac9426b HEAD@{14}: rebase (finish): returning to refs/heads/main
ac9426b HEAD@{15}: rebase (pick): created test3.txt
fbeecd6 HEAD@{16}: rebase (start): checkout feature
5582bbf HEAD@{17}: commit: created test3.txt
ad53963 (origin/main) HEAD@{18}: checkout: moving from feature to main
fbeecd6 HEAD@{19}: commit: test2.txt
ad53963 (origin/main) HEAD@{20}: checkout: moving from main to feature
ad53963 (origin/main) HEAD@{21}: Branch: renamed refs/heads/master to refs/heads/main
ad53963 (origin/main) HEAD@{23}: commit (initial): first commit


Git Branches commands
 ================================================================================
15.git branch -a - List all of the branches in your repo.Add a <branch> argument to create a new branch with the 
                   name<branch>.
16.git checkout -b <branch_name> - Create and check out a new branch named <branch>. Drop the -b flag to checkout 
                                   an existing branch

17.git merge <branch> - Merge<branch> into the current branch.

akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
b3d97f3 (HEAD -> feature) 3
e432e43 2
ae6ee03 1
7c64c2d (main) c1
48a75fa c0
c3ed8a0 (origin/main) first commit
akhilpagadapoola@Akhils-MacBook-Air test % git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)
akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
7c64c2d (HEAD -> main) c1
48a75fa c0
c3ed8a0 (origin/main) first commit
akhilpagadapoola@Akhils-MacBook-Air test % git merge feature
Updating 7c64c2d..b3d97f3
Fast-forward
 1 | 0
 2 | 0
 3 | 0
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 1
 create mode 100644 2
 create mode 100644 3
akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline
b3d97f3 (HEAD -> main, feature) 3
e432e43 2
ae6ee03 1
7c64c2d c1
48a75fa c0
c3ed8a0 (origin/main) first commit
akhilpagadapoola@Akhils-MacBook-Air test %


Remote Repositories Commands
----------------------------
18. git remote add <name> <url>- Create a new connection to a remote repo. After adding a remote,you can use, 
    <name> as a shortcut for <url> in other commands.

   git init
   touch alpha.txt
   git add .
   git commit -m "first commit"
   git remote add origin https://github.com/akhilgit19/test.git
   git rebase origin/main
   git log --oneline
   akhilpagadapoola@Akhils-MacBook-Air test % git log --oneline                                           
   029d7f7 (HEAD -> master) first commit
   612ccaf (origin/main) Initial commit
   git switch main
   git merge master
   git push origin main
   
19. git fetch <remote> <branch>- Fetches a specific <branch>, from the repo.Leave off<branch> to fetch all 
             1                    remote refs.
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

akhilpagadapoola@Akhils-MacBook-Air test % git config --global alias.glog "log --graph --oneline"
akhilpagadapoola@Akhils-MacBook-Air test % git glog
* dacdf7b (HEAD -> main, origin/main) del pyt
*   061c435 Merge pull request #1 from akhilgit19/feature
|\  
| * 8577b00 (origin/feature) feature
|/  
* 5b0ba80 first commit

25.git config --system core.editor <editor>-Set text editor used by commands for all users on the machine. <editor>arg should be the command that launches the desired editor (e.g., vi).

26.git config --global --edit - Open the global configuration file in a text editor for manual editing.

akhilpagadapoola@Akhils-MacBook-Air test % git config --global --edit
hint: Waiting for your editor to close the file... 
[user]
        name = akhilgit19
        email = akhilpagadapoola123@gmail.com
[pull]
        rebase = false
[alias]
        glog = log --graph --oneline
~                                                                                                                                                                                
akhilpagadapoola@Akhils-MacBook-Air test % git config --global --list
user.name=akhilgit19
user.email=akhilpagadapoola123@gmail.com
pull.rebase=false
alias.glog=log --graph --oneline



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


47.git branch -D branch_name
48.git branch -M main (it will rename the branch name)

49. git stash
50. git stash list
51. git stash pop
52. git stah drop


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


command updated:
akhilpagadapoola@Akhils-MacBook-Air test % curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer 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" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/akhilgit19/PRIME10-DEVOPS/branches 


Solution
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



Forking A Repository On Github
-------------------------------------------
What is forking and how does it work? To Fork a project you are basically cloning
someone else’s original project from Github and adding it to your repository. This
will allow you to modify the project without interfering with the owner’s original
project.
1)Head over to Github and create an account if you don’t have one already.
2)Next search for the repository you would like to fork.
3)Click the fork button in the upper-righthand corner to add to your repository.
To add this forked project to our local machine, we will go back into our terminal and
type the command

Clone The Forked Repo
-----------------------
git clone https://github.com/your-username/forked-repo.git
Make Changes :-
------------------
git add . # To stage the changes
git commit -m "Enter Your commit message here"
git push origin main # Replace 'main' with the branch you want to push to.
Updating Your Fork: 
---------------------
If you wanna keep your forked repo up-to-date with
the latest awesomeness from the original repo, no worries! Here’s the secret
sauce! First, add the original repo as an “upstream” remote with this
command:
git remote add upstream
https://github.com/original-repo-owner/original-repo.git

Then, fetch all the juicy changes from the upstream repo using:
-----------------------------------------------------------------
git fetch upstream
Now, it’s time to merge those updates into your local repo! Just

switch to the branch you wanna update (usually ‘master’) and run:
-----------------------------------------------------------------------
git checkout master
git merge upstream/master # Replace 'master' with your branch name if
it's different.
git push origin master










                                                     LINUX
==============================================================================================================

 https://github.com/praveen1994dec/Knowledge_Base.git

Logs:

         
     SSL/TLS                UDP/TCP/
User-------------> Request------------------> Regional server---------> DNS Server



1. Ping:
===================================
Purpose: To check the reachability of a host on an Internet Protocol (IP)
network.
Usage Example: ping google.com

akhilpagadapoola@Akhils-MacBook-Air ~ % ping google.com
PING google.com (142.250.195.110): 56 data bytes
64 bytes from 142.250.195.110: icmp_seq=0 ttl=55 time=22.666 ms
64 bytes from 142.250.195.110: icmp_seq=1 ttl=55 time=67.757 ms
64 bytes from 142.250.195.110: icmp_seq=2 ttl=55 time=33.472 ms
64 bytes from 142.250.195.110: icmp_seq=3 ttl=55 time=60.244 ms
64 bytes from 142.250.195.110: icmp_seq=4 ttl=55 time=30.264 ms

2. Traceroute (or traceroute6):
======================================
Purpose: To display the route and measure transit delays of packets across an
Internet Protocol network.
Usage Example: traceroute google.com

akhilpagadapoola@Akhils-MacBook-Air ~ % traceroute google.com
traceroute to google.com (142.250.195.110), 64 hops max, 52 byte packets
 1  172.20.10.1 (172.20.10.1)  4.986 ms  4.561 ms  3.784 ms
 2  100.64.0.100 (100.64.0.100)  145.373 ms  190.336 ms  201.034 ms
 3  192.168.27.154 (192.168.27.154)  16.888 ms
    192.168.27.158 (192.168.27.158)  18.311 ms  13.785 ms
 4  192.168.28.18 (192.168.28.18)  15.178 ms  18.244 ms  15.133 ms
 5  192.168.28.49 (192.168.28.49)  15.114 ms  19.953 ms  17.953 ms
 6  * * *
 7  125.18.92.77 (125.18.92.77)  39.321 ms  17.756 ms
    125.18.92.137 (125.18.92.137)  14.844 ms
 8  116.119.68.247 (116.119.68.247)  23.189 ms
    182.79.243.201 (182.79.243.201)  24.294 ms  51.116 ms
 9  72.14.205.196 (72.14.205.196)  26.582 ms  28.362 ms  32.187 ms
10  * * *
11  74.125.252.90 (74.125.252.90)  83.450 ms
    142.251.55.90 (142.251.55.90)  34.901 ms
    216.239.47.142 (216.239.47.142)  26.572 ms
12  172.253.75.14 (172.253.75.14)  31.451 ms
    142.251.230.90 (142.251.230.90)  20.453 ms
    142.251.55.69 (142.251.55.69)  36.297 ms
13  maa03s39-in-f14.1e100.net (142.250.195.110)  26.802 ms  28.112 ms  27.130 ms
akhilpagadapoola@Akhils-MacBook-Air ~ %

When you ran:

nginx
Copy
Edit
traceroute google.com
It showed the path from your device to google.com (142.250.195.110) through up to 64 hops, using 52-byte packets.

Let’s go line by line:

Copy
Edit
 1  172.20.10.1           4.986 ms  4.561 ms  3.784 ms
Hop 1: Your local router or gateway (likely your phone hotspot or home Wi-Fi).

The three numbers are three round-trip time (RTT) measurements in milliseconds.

Copy
Edit
 2  100.64.0.100         145.373 ms  190.336 ms  201.034 ms
Hop 2: An internal carrier-grade NAT address, common in ISP networks.

High delay here might indicate congestion.

markdown
Copy
Edit
 3  192.168.27.154       16.888 ms
    192.168.27.158       18.311 ms  13.785 ms
Hop 3: Shows multiple possible routers at the same hop (load balancing).

These are also private IPs, still within your ISP’s internal routing.

pgsql
Copy
Edit
 4-5**: More internal hops** with similar latencies. 
Copy
Edit
 6  * * *
Hop 6: No response. The router didn’t reply (often due to a firewall or ICMP being blocked).

markdown
Copy
Edit
 7-12**: These are public IPs**
- You’re now outside private networks, reaching ISP routers and peering points.
- IPs like `125.18.92.77`, `72.14.205.196`, and `142.251.55.69` belong to ISPs or Google’s network.

13 maa03s39-in-f14.1e100.net (142.250.195.110)

yaml
Copy
Edit
- **Final Destination**: You reached Google’s server.
- `maa03s39` likely indicates a **data center in Chennai (MAA = Chennai Airport Code)**.

---

### 💡 Key Notes:
- Three RTT values are shown for each hop to detect variability.
- `* * *` indicates lost or blocked probes.
- Private IPs (`192.168.x.x`, `100.64.x.x`, etc.) indicate internal ISP routing.

---

Would you like me to help you visualize this as a path diagram?


You said:


🌐 Visualizing the Traceroute Path
The traceroute output you provided indicates the following hops:

Your Local Router: 172.20.10.1

ISP's Internal Router: 100.64.0.100

Intermediate Routers: 192.168.27.154, 192.168.27.158, 192.168.28.18, 192.168.28.49

Public ISP Routers: 125.18.92.77, 182.79.243.201, 72.14.205.196, 74.125.252.90, 142.251.230.90

Google's Server: 142.250.195.110

Here's a simplified path diagram illustrating the hops:

plaintext
Copy
Edit
Your Device (Bengaluru)
       |
       v
Local Router (172.20.10.1)
       |
       v
ISP Router (100.64.0.100)
       |
       v
Intermediate Routers
       |
       v
Public ISP Routers
       |
       v
Google's Server (142.250.195.110)

3. Netstat:
========================================================
Purpose: To display active network connections, routing tables, interface
statistics, masquerade connections, and multicast memberships.
Usage Example: netstat -a

akhilpagadapoola@Akhils-MacBook-Air ~ % netstat -a
Active Internet connections (including servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)    
tcp6       0      0  2401:4900:4e74:f.61920 2600:9000:2179:7.https ESTABLISHED
tcp4       0      0  172.20.10.4.61919      lb-140-82-114-22.https ESTABLISHED
tcp4       0      0  172.20.10.4.61918      lb-140-82-114-22.https ESTABLISHED
tcp4       0      0  172.20.10.4.61917      20.207.73.85.https     ESTABLISHED
tcp4       0      0  172.20.10.4.61880      76.191.118.28.https    ESTABLISHED
tcp4       0      0  172.20.10.4.61597      aa1ba9bef7b18c26.https ESTABLISHED
tcp6       0      0  2401:4900:4e74:f.61596 si-in-f188.1e100.5228  ESTABLISHED
tcp4       0      0  172.20.10.4.61576      lb-140-82-113-25.https ESTABLISHED
tcp4       0      0  172.20.10.4.61574      172.20.10.1.60782      ESTABLISHED
tcp6       0      0  *.61574                *.*                    LISTEN     
tcp4       0      0  *.61574                *.*                    LISTEN     
tcp6       0      0  akhils-macbook-a.black fe80::d196:404d:.1026  ESTABLISHED
tcp6       0      0  akhils-macbook-a.1024  fe80::d196:404d:.1024  ESTABLISHED
tcp4       0      0  192.168.29.120.64229   del12s06-in-f14..https CLOSE_WAIT 
tcp4      31      0  192.168.29.120.64224   www.eclipse.org.https  CLOSE_WAIT 
tcp4       0      0  192.168.29.120.64220   49.44.131.112.https    ESTABLISHED
tcp4       0      0  192.168.29.120.64219   49.44.131.112.https    ESTABLISHED
tcp4       0      0  192.168.29.120.64218   49.44.131.112.https    ESTABLISHED
tcp4       0      0  192.168.29.120.64217   49.44.131.112.https    ESTABLISHED
tcp4       0      0  192.168.29.120.64215   49.44.131.112.https    ESTABLISHED
tcp4       0      0  localhost.9922         *.*                    LISTEN     
tcp6       0      0  *.commplex-main        *.*                    LISTEN     
tcp4       0      0  *.commplex-main        *.*                    LISTEN     
tcp6       0      0  *.afs3-fileserver      *.*                    LISTEN     
tcp4       0      0  *.afs3-fileserver      *.*                    LISTEN     
tcp46      0      0  *.mysql                *.*                    LISTEN     
tcp46      0      0  *.33060                *.*                    LISTEN     
tcp4       0      0  localhost.intu-ec-clie *.*                    LISTEN     
tcp6       0      0  localhost.intu-ec-clie *.*                    LISTEN     
tcp6       0      0  2401:4900:4e74:f.61908 2600:9000:2179:7.https TIME_WAIT  
tcp6       0      0  2401:4900:4e74:f.61909 2600:9000:2179:7.https TIME_WAIT  
tcp6       0      0  2401:4900:4e74:f.61911 2600:9000:2179:7.https TIME_WAIT  
tcp6       0      0  2401:4900:4e74:f.61912 2600:9000:2179:7.https TIME_WAIT  
tcp4       0      0  172.20.10.4.54268      17.242.13.6.5223       ESTABLISHED
tcp4       0      0  172.20.10.4.54254      whatsapp-chatd-e.443   ESTABLISHED
     
udp6       0      0  2401:4900:4e74:f.54178 maa03s35-in-x03..https            
udp4       0      0  *.57290                *.*                               
udp4       0      0  172.20.10.4.63135      bom12s13-in-f10..https            
udp4       0      0  172.20.10.4.56710      bom07s25-in-f14..https            
udp4       0      0  172.20.10.4.58944      bom12s13-in-f10..https            
udp4       0      0  172.20.10.4.56976      maa03s37-in-f14..https            
udp4       0      0  172.20.10.4.62302      104.18.41.41.https                
udp4       0      0  172.20.10.4.52648      bom07s25-in-f14..https            
udp4       0      0  *.xserveraid           *.*                               
udp4       0      0  172.20.10.4.57583      bom07s30-in-f10..https            
udp4       0      0  *.*                    *.*                               
                         
udp4       0      0  *.*                    *.*                               
udp4       0      0  *.*                    *.*                               
                        
udp4       0      0  *.*                    *.*                               
udp46      0      0  *.*                    *.*                               
udp4       0      0  *.netbios-ns           *.*                               
udp4       0      0  *.netbios-dgm          *.*                               
icm4    4524      0  *.*                    *.*                               
Active Multipath Internet connections
Proto/ID  Flags      Local Address          Foreign Address        (state)    
icm6       0      0  *.*                    *.*                               
Active LOCAL (UNIX) domain sockets
Address          Type   Recv-Q Send-Q            Inode             Conn             Refs          Nextref Addr
3c34f15613c38a3f stream      0      0                0 3c34f15613c38977                0                0 
3c34f15613c3058f stream      0      0                0 3c34f15613c303ff                0                0
3c34f15613c303ff stream      4      0                0 3c34f15613c3058f                0                0
3c34f15613c2c967 stream      0      0                0 3c34f15613c2c0cf                0                0 /var/run/mDNSResponder
3c34f15613c2c0cf stream      0      0                0 3c34f15613c2c967                0                0
3c34f15613c2bb57 stream      0      0                0 3c34f15613c339e7                0                0 /var/run/mDNSResponder
3c34f15613c339e7 stream      0      0                0 3c34f15613c2bb57                0                0
/var/run/mDNSResponder
3c34f15613c3ab0f stream      0      0                0 3c34f15613c3b46f                0                0
3c34f15613c31c37 stream      0      0                0 3c34f15613c31b6f                0                0 /var/run/mDNSResponder
3c34f15613c31b6f stream      0      0                0 3c34f15613c31c37                0                0
3c34f15613c30017 stream      0      0                0 3c34f15613c2ff4f                0                0 /var/run/mDNSResponder
3c34f15613c2ff4f stream      0      0                0 3c34f15613c30017                0                0
3c34f15613c37077 stream      0      0                0 3c34f15613c34647                0                0 /var/run/mDNSResponder
3c34f15613c34647 stream      0      0                0 3c34f15613c37077                0                0
3c34f15613c31147 stream      0      0                0 3c34f15613c3107f                0                0 /var/run/mDNSResponder
3c34f15613c3107f stream      0      0                0 3c34f15613c31147                0                0
3c34f15613c30337 stream      0      0                0 3c34f15613c3826f                0                0 /var/run/mDNSResponder
3c34f15613c3826f stream      0      0                0 3c34f15613c30337                0                0
3c34f15613c3696f stream      0      0                0                0                0                0
3c34f15613c363f7 stream      0      0                0 3c34f15613c3551f                0                0 /var/run/mDNSResponder
3c34f15613c3551f stream      0      0                0 3c34f15613c363f7                0                0
3c34f15613c3ac9f stream      0      0                0 3c34f15613c3abd7                0                0 /var/run/mDNSResponder
3c34f15613c3abd7 stream      0      0                0 3c34f15613c3ac9f                0                0
3c34f15613c2ea37 stream      0      0                0 3c34f15613c2e96f                0                0
3c34f15613c2e96f stream      0      0                0 3c34f15613c2ea37                0                0
3c34f15613c2e8a7 stream      0      0                0 3c34f15613c2e7df                0                0
3c34f15613c2e7df stream      0      0                0 3c34f15613c2e8a7                0                0
3c34f15613c2e717 stream      0      0                0 3c34f15613c2e64f                0                0
3c34f15613c2e64f stream      0      0                0 3c34f15613c2e717                0                0
3c34f15613c2e587 stream      0      0                0 3c34f15613c2e4bf                0                0
3c34f15613c2e4bf stream      0      0                0 3c34f15613c2e587                0                0
3c34f15613c2e3f7 stream      0      0                0 3c34f15613c2e32f                0                0
3c34f15613c33ce7 dgram       0      0                0 3c34f15613c33c1f                0                0
3c34f15613c33c1f dgram       0      0 3c34f14c7b8bdfdf                0 3c34f15613c388af                0 /private//var/run/syslog
unexpected kind 242 which 0xf2
Registered kernel control modules
id       flags    pcbcount rcvbuf   sndbuf   name 
       1        5        0     8192    32768 com.apple.network.tcp_ccdebug 
       2       28        1     8192   131072 com.apple.flow-divert 
       3        1       39    65536    65536 com.apple.net.netagent 
       4        9        0   524288   524288 com.apple.content-filter 
       5       29        6   524288   524288 com.apple.net.utun_control 
       6       21        0    65536    65536 com.apple.net.ipsec_control 
       7        0       42     8192     2048 com.apple.netsrc 
       8       18        3     8192     2048 com.apple.network.statistics 
       9        1        0     8192     2048 com.apple.network.advisory 
       a        1        0    65536    65536 com.apple.net.rvi_control 
       b        1        0    16384     2048 com.apple.nke.sockwall 
       c        4        0    65536     2048 com.apple.spmi.nfc 
       d        4        0    65536     2048 com.apple.uart.wlan-debug 
       e        4        0     8192     2048 com.apple.uart.sk.wlan-debug 
Active kernel event sockets
Proto Recv-Q Send-Q vendor  class  subcl
kevt       0      0      1      1      9
kevt       0      0      1      1      2
kevt       0      0      1      6      1
kevt       0      0      1      1      6
kevt       0      0      1      1      1
kevt       0      0      1      1      2



You're looking at the complete output of the netstat -a command on your Mac, and it's a very detailed snapshot of your system’s current network activity and socket status. Let's break this down section by section so you clearly understand what's going on.

🔍 1. What Is netstat -a?
netstat -a shows all active connections and listening ports on your machine, including:

TCP/UDP over IPv4 & IPv6

Listening services

Local ↔ Remote connections

Unix domain sockets

Kernel socket info (like multicast, masquerade, etc.)

🧱 2. Section-by-Section Explanation
✅ Active Internet Connections (TCP/UDP)
Key Columns:
Column	Meaning
Proto	Protocol: tcp, udp, with 4 or 6 for IPv4/IPv6
Recv-Q	Bytes in queue waiting to be received
Send-Q	Bytes waiting to be sent
Local Address	Your device’s IP and port
Foreign Addr	Remote IP and port you’re communicating with
(state)	TCP state: ESTABLISHED, LISTEN, CLOSE_WAIT, TIME_WAIT, etc.

🔗 Examples from your output:
nginx
Copy
Edit
tcp4       0      0  172.20.10.4.61919      lb-140-82-114-22.https  ESTABLISHED
A TCP connection from your device to a remote server (possibly GitHub) on port 443 (HTTPS).

Connection is active and functioning.

nginx
Copy
Edit
tcp4       0      0  *.commplex-main        *.*                    LISTEN
A local service is listening for incoming connections on this port.

*.* means it’s listening on all interfaces and from all remote ports.

ruby
Copy
Edit
tcp6       0      0  2401:4900:4e74:f.61596 si-in-f188.1e100.5228  ESTABLISHED
An IPv6 connection to a Google server (1e100.net is a Google domain).

💤 Common TCP States:
State	Meaning
ESTABLISHED	Active connection in use (data can be sent/received)
LISTEN	Local app is waiting for incoming connections
CLOSE_WAIT	Remote closed, local app hasn’t closed yet
TIME_WAIT	Connection closed; OS waiting to make sure all data is processed

📡 UDP Entries
UDP is connectionless, so no ESTABLISHED/LISTEN states.

Shows which UDP ports are in use or open.

Example:

nginx
Copy
Edit
udp4       0      0  172.20.10.4.62302      104.18.41.41.https
You're sending data over UDP to IP 104.18.41.41 (Cloudflare or similar).

📁 Active UNIX Domain Sockets
This section shows internal inter-process communication (IPC) on your local system.

These are used by services (e.g., mDNSResponder) for local-only communication.

Example:

arduino
Copy
Edit
/var/run/mDNSResponder
Your machine is using this socket to resolve .local hostnames (e.g., AirDrop, Bonjour).

🧠 Special Sections Explained
🔁 Multipath Internet Connections
Rare, advanced routing or redundant networking setups (e.g., Apple’s network multipath).

⚙️ Registered Kernel Control Modules
These are internal Apple network control interfaces like:

flow-divert (used by VPNs)

ipsec_control

network.statistics

🎯 Active Kernel Event Sockets
Low-level kernel event listeners. You usually won't need to deal with these unless debugging system-level networking.

🗺️ Summary Diagram (Textual)
less
Copy
Edit
[Your MacBook]
   |
   |---> [Google: 1e100.net:5228]         (TCP/ESTABLISHED)
   |---> [GitHub: lb-140-82-114-22:443]   (TCP/ESTABLISHED)
   |---> [Localhost Services]             (TCP/Listening on MySQL, afs3, etc.)
   |---> [Cloudflare: 104.18.41.41:443]   (UDP traffic)
   |---> [mDNSResponder]                  (UNIX domain socket)

4. Nmap:
==========================================================
Purpose: To discover hosts and services on a computer network, creating a
"map" of the network.
Usage Example: nmap -p 1-1000 target



Nmap (Network Mapper) is used to:

Discover devices (hosts) on a network

Detect open ports on a target machine

Identify running services and operating systems

Perform security audits or vulnerability scans

🧪 Command Example:
bash
Copy
Edit
nmap -p 1-1000 target
🔧 Breakdown:
nmap: The tool itself

-p 1-1000: Scan ports 1 through 1000

target: This can be an IP address, hostname, or domain (e.g., 192.168.1.1, google.com, etc.)

📘 Example Output:
Let’s say you run:

bash
Copy
Edit
nmap -p 1-1000 192.168.1.10
You might get:

kotlin
Copy
Edit
Starting Nmap 7.91 ( https://nmap.org ) at 2025-05-04
Nmap scan report for 192.168.1.10
Host is up (0.0012s latency).
Not shown: 996 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https
631/tcp  open  ipp
📖 Interpretation:
Port	State	Service
22	open	SSH (secure shell access)
80	open	HTTP (web server)
443	open	HTTPS (secure web server)
631	open	IPP (Internet Printing Protocol)

This tells you:

The machine at 192.168.1.10 is online

It is running services on ports 22, 80, 443, and 631

Each open port corresponds to a known network service

🎯 Real-World Use Cases
Sysadmins use it to audit what services are running on devices.

Pentesters use it to find vulnerabilities by seeing what ports/services are exposed.

Network engineers use it to map out entire subnets.



🆚 Netstat vs. Nmap – Key Differences
===========================================
Feature	netstat	nmap
🔍 Purpose	Shows local system’s network connections	Scans remote systems/networks for open ports
👤 Perspective	Internal (local machine)	External (targeting other machines)
📡 Usage	Monitoring, debugging, checking active sockets	Network discovery, security auditing, vulnerability scanning
📄 Output	List of active connections, ports in use, listeners	List of detected hosts, open ports, running services
🔒 Security Use	Basic monitoring	Full security scans / footprinting
📥 Installation	Built into most OSes	Needs to be installed (nmap package)
⚙️ Example	netstat -a (all connections)	nmap -p 1-1000 target.com (port scan)



5. Tcpdump:
========================
Purpose: To capture and analyze network traffic.
Usage Example: tcpdump -i eth0



🐾 Tcpdump – Explained
✅ Purpose:
tcpdump is a command-line packet analyzer. It’s used to capture and inspect network traffic that passes through an interface (like Ethernet or Wi-Fi) on your machine.

🔧 Basic Usage:
bash
Copy
Edit
tcpdump -i eth0
📖 What it means:
tcpdump: The tool

-i eth0: Capture packets on the eth0 interface (typically a wired Ethernet interface)

⚠️ You may need sudo privileges to run it.

🎯 What It Does:
This command listens to all packets going in/out of the eth0 network interface and displays:

Source and destination IPs

Protocols (TCP, UDP, ICMP, etc.)

Port numbers

Flags (SYN, ACK, FIN, etc.)

Timestamps

Packet details (headers, sizes)

📘 Sample Output:
bash
Copy
Edit
12:34:56.789012 IP 192.168.1.10.54321 > 142.250.195.110.443: Flags [S], seq 12345, win 65535, length 0
🔍 Explanation:
192.168.1.10.54321: Your local machine's IP and source port

142.250.195.110.443: Target IP (e.g. Google) and destination port (443 for HTTPS)

Flags [S]: A SYN packet (starting a TCP connection)

seq 12345: Sequence number of the packet

length 0: No data in this packet

💡 Common Tcpdump Use Cases:
------------------------------
Debugging network issues (latency, dropped packets)

Detecting unusual or malicious traffic

Verifying if packets are reaching a destination

Network performance tuning

Real-time monitoring of specific traffic (e.g. DNS, HTTP)

🧪 More Examples:
Capture only HTTP traffic:

tcpdump -i eth0 port 80
Save to a file for later analysis:

bash
Copy
Edit
tcpdump -i eth0 -w capture.pcap
Read from a .pcap file:

bash
Copy
Edit
tcpdump -r capture.pcap

6. Ipconfig (Windows) / ifconfig (Linux):
================================================
Purpose: To display the configuration of network interfaces.
Usage Example (Linux): ifconfig


akhilpagadapoola@Akhils-MacBook-Air ~ % ifconfig
lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
	options=1203<RXCSUM,TXCSUM,TXSTATUS,SW_TIMESTAMP>
	inet 127.0.0.1 netmask 0xff000000
	inet6 ::1 prefixlen 128 
	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1 
	nd6 options=201<PERFORMNUD,DAD>
gif0: flags=8010<POINTOPOINT,MULTICAST> mtu 1280
stf0: flags=0<> mtu 1280
anpi1: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether e2:45:d0:05:0a:9e
	media: none
	status: inactive
anpi0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether e2:45:d0:05:0a:9d
	media: none
	status: inactive
en3: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether e2:45:d0:05:0a:7d
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en4: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether e2:45:d0:05:0a:7e
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en1: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:84:1c:ce:24:c0
	media: autoselect <full-duplex>
	status: inactive
en2: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:84:1c:ce:24:c4
	media: autoselect <full-duplex>
	status: inactive
ap1: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether fe:e2:6c:06:04:d3
	inet6 fe80::fce2:6cff:fe06:4d3%ap1 prefixlen 64 scopeid 0xa 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect (<unknown type>)
	status: inactive
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether fc:e2:6c:06:04:d3
	inet6 fe80::454:cf89:3d12:fcc2%en0 prefixlen 64 secured scopeid 0xb 
	inet 172.20.10.4 netmask 0xfffffff0 broadcast 172.20.10.15
	inet6 2401:4900:4e52:53df:1c1d:b9dc:734c:cf04 prefixlen 64 autoconf secured 
	inet6 2401:4900:4e52:53df:30e3:e412:17d4:ad26 prefixlen 64 autoconf temporary 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
bridge0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=63<RXCSUM,TXCSUM,TSO4,TSO6>
	ether 36:84:1c:ce:24:c0
	Configuration:
		id 0:0:0:0:0:0 priority 0 hellotime 0 fwddelay 0
		maxage 0 holdcnt 0 proto stp maxaddr 100 timeout 1200
		root id 0:0:0:0:0:0 priority 0 ifcost 0 port 0
		ipfilter disabled flags 0x0
	member: en1 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 8 priority 0 path cost 0
	member: en2 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 9 priority 0 path cost 0
	nd6 options=201<PERFORMNUD,DAD>
	media: <unknown type>
	status: inactive
awdl0: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether e6:41:f3:1e:bc:ef
	inet6 fe80::e441:f3ff:fe1e:bcef%awdl0 prefixlen 64 scopeid 0xd 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
llw0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether e6:41:f3:1e:bc:ef
	inet6 fe80::e441:f3ff:fe1e:bcef%llw0 prefixlen 64 scopeid 0xe 
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: inactive
utun0: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::47f2:1b12:5eda:2113%utun0 prefixlen 64 scopeid 0xf 
	nd6 options=201<PERFORMNUD,DAD>
utun1: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 2000
	inet6 fe80::c060:d5c5:279c:b7c4%utun1 prefixlen 64 scopeid 0x10 
	nd6 options=201<PERFORMNUD,DAD>
utun2: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1000
	inet6 fe80::ce81:b1c:bd2c:69e%utun2 prefixlen 64 scopeid 0x11 
	nd6 options=201<PERFORMNUD,DAD>
utun3: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1500
	inet6 fe80::296d:d5ce:1703:e983%utun3 prefixlen 64 scopeid 0x12 
	nd6 options=201<PERFORMNUD,DAD>

🔧 Command Purpose
ifconfig (short for interface configuration) is used on Unix/Linux/macOS systems to:

View or configure network interfaces (NICs).

Display IP addresses, MAC addresses, status, etc.

In macOS or Linux, you just run:

bash
Copy
Edit
ifconfig
This shows the network interfaces and their configurations.

🧵 Your Output (Line-by-Line Explanation)
▶ lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
lo0: This is the loopback interface (used to communicate with itself, i.e., localhost).

flags: Show status:

UP: Interface is enabled.

LOOPBACK: Internal communication.

RUNNING: Operational.

MULTICAST: Supports multicast traffic.

mtu 16384: Maximum Transmission Unit (size of packets it can handle).

options=1203<RXCSUM,TXCSUM,TXSTATUS,SW_TIMESTAMP>
These are interface options like checksum offloading (hardware helps with data verification) and timestamping.

inet 127.0.0.1 netmask 0xff000000
IPv4 address for loopback: 127.0.0.1

netmask 0xff000000: Same as 255.0.0.0 (subnet mask).

inet6 ::1 prefixlen 128
IPv6 version of 127.0.0.1 is ::1, used for self-communication.

inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1
A link-local IPv6 address, only usable within the device/network segment.

nd6 options=201<PERFORMNUD,DAD>
ND6: IPv6 neighbor discovery options:

PERFORMNUD: Checks if neighbors are reachable.

DAD: Duplicate Address Detection.

Now let’s go over other interfaces. Each block like this shows another interface.

🧷 en0 - Your active Wi-Fi interface
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
en0: Ethernet or Wi-Fi interface (usually Wi-Fi).

UP: Enabled.

RUNNING: Working.

BROADCAST: Can send to all on the network.

MULTICAST: Supports multicast traffic.

SIMPLEX: Can’t hear its own transmissions.

mtu 1500: Normal MTU for Ethernet/Wi-Fi.

options=6460<TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
Various offloading and checksum options for performance.

ether fc:e2:6c:06:04:d3
MAC address of this interface (physical ID).

inet6 fe80::...%en0 and inet6 2401:4900:...
Several IPv6 addresses:

fe80::...: Link-local IPv6.

Others are global IPv6 addresses (publicly routable).

inet 172.20.10.4 netmask 0xfffffff0 broadcast 172.20.10.15
IPv4 address: 172.20.10.4

netmask: 255.255.255.240 – defines network range.

broadcast: Last address in that subnet – used to send to all devices.

status: active
This interface is currently in use and online.

❌ Interfaces marked status: inactive
Examples:

bash
Copy
Edit
en1, en2, anpi0, anpi1, ap1, bridge0, llw0
These are:

Either physical interfaces not connected.

Virtual interfaces.

Bridges or auxiliary connections.

en1, en2: Often Thunderbolt/Ethernet adapters.
bridge0: Software bridge between interfaces (like en1/en2).
awdl0: Apple Wireless Direct Link – used for AirDrop, AirPlay.
utun0, utun1...: Virtual interfaces used for VPNs.
✅ Summary Table of Fields
Field	Meaning
flags	Interface capabilities & state
inet	IPv4 address
inet6	IPv6 address
ether	MAC address
mtu	Max transmission unit (packet size)
status	Whether interface is active
options	Offloading & performance options
media	Connection type (e.g., full-duplex)

✅ TL;DR
The ifconfig output gives you a snapshot of all your network interfaces, showing:

Which ones are up or down

IP/MAC addresses

Technical details like MTU, media type, etc.




7. Dig (Domain Information Groper):
=========================================
Purpose: To query DNS name servers for information about host addresses,
mail exchanges, name servers, and related information.
Usage Example: dig google.com


akhilpagadapoola@Akhils-MacBook-Air ~ % dig google.com

; <<>> DiG 9.10.6 <<>> google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 4141
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;google.com.			IN	A

;; ANSWER SECTION:
google.com.		295	IN	A	142.250.71.110

;; Query time: 59 msec
;; SERVER: fe80::ec28:d3ff:fe51:5464%11#53(fe80::ec28:d3ff:fe51:5464%11)
;; WHEN: Tue May 13 10:47:18 IST 2025
;; MSG SIZE  rcvd: 55

akhilpagadapoola@Akhils-MacBook-Air ~ % 

🔧 Purpose
dig is used to:

Query DNS servers

Get info about domains like:

IP addresses (A records)

Mail servers (MX records)

Name servers (NS records)

And more.

✅ Command used:
bash
Copy
Edit
dig google.com
Now let's go line-by-line through your output:

akhilpagadapoola@Akhils-MacBook-Air ~ % dig google.com
You, the user akhilpagadapoola, executed the command in Terminal on your Mac.

dig google.com: You're querying DNS for A record (default) of google.com.

; <<>> DiG 9.10.6 <<>> google.com
This is the version banner.

DiG 9.10.6: You’re using version 9.10.6 of dig.

It echoes the query: google.com.

;; global options: +cmd
This shows the default command-line options being used.

+cmd is just a flag to display command formatting in output.

;; Got answer:
This line indicates that a DNS response was received.

;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 4141
This is the DNS header info. Let’s break it down:

opcode: QUERY: Type of DNS message (a standard query).

status: NOERROR: No error in response. The domain exists.

id: 4141: Random query ID used to match request/response.

;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
flags: DNS flags set in the response:

qr: Query Response (this is a response).

rd: Recursion Desired (you asked the server to fetch answer recursively).

ra: Recursion Available (server supports recursive queries).

QUERY: 1: You asked 1 question (google.com A record).

ANSWER: 1: One answer was received.

AUTHORITY: 0: No authoritative name server listed in the reply.

ADDITIONAL: 1: One extra record (usually metadata or EDNS info).

;; OPT PSEUDOSECTION:
This is a special section (not from actual DNS zones) for EDNS (Extended DNS).

Used to improve DNS performance and add features.

; EDNS: version: 0, flags:; udp: 4096
EDNS: Extended DNS version 0 (standard).

udp: 4096: Your system can handle DNS responses up to 4096 bytes over UDP.

;; QUESTION SECTION:
Shows what was asked in the query.

;google.com. IN A
You asked for the A (Address) record of google.com.

IN: Internet class (standard).

A: IPv4 address.

;; ANSWER SECTION:
This contains the actual answer returned by the DNS server.

google.com. 295 IN A 142.250.71.110
Breakdown:

google.com.: The domain.

295: TTL (Time To Live) in seconds – how long this record is valid in cache.

IN: Internet.

A: Address record (IPv4).

142.250.71.110: This is Google’s IP address.

;; Query time: 59 msec
The entire DNS lookup took 59 milliseconds.

;; SERVER: fe80::ec28:d3ff:fe51:5464%11#53(fe80::ec28:d3ff:fe51:5464%11)
This is the DNS server that responded.

It's an IPv6 link-local address on interface %11.

#53: Port 53 (standard DNS port).

;; WHEN: Tue May 13 10:47:18 IST 2025
When the query was made – timestamp from your system clock.

;; MSG SIZE rcvd: 55
The DNS response size in bytes (55 bytes total received).

🧠 Summary (TL;DR)
Section	Meaning
HEADER	Metadata about the query/response
QUESTION	What you asked (google.com A record)
ANSWER	The answer (Google’s IP address)
AUTHORITY	Shows DNS servers for the domain (none here)
ADDITIONAL	Extra DNS info (like EDNS)
SERVER	The DNS server that answered
TIME	How long the query took
SIZE	Size of the DNS reply



8. Nslookup (Windows) / host (Linux):
===========================================
Purpose: To query DNS servers for domain information.

8. Nslookup / host
✅ Purpose
Both tools are used to query DNS servers for domain-related information such as:

IP addresses of domain names (A or AAAA records)

Domain names of IP addresses (reverse lookup)

Mail servers (MX records)

Name servers (NS records)

🖥️ 1. Using nslookup (Windows, macOS, Linux)
📌 Example:
bash
Copy
Edit
nslookup google.com
🔍 Sample Output Explained:
bash
Copy
Edit
Server:         192.168.1.1
Address:        192.168.1.1#53

Non-authoritative answer:
Name:   google.com
Address: 142.250.71.110
✅ Line-by-line:
Server: 192.168.1.1 – This is the DNS server being used for the lookup.

Address: 192.168.1.1#53 – It used port 53 (standard for DNS).

Non-authoritative answer: – The DNS info came from cache or a recursive DNS server, not directly from Google’s authoritative name server.

Name: google.com – The domain queried.

Address: 142.250.71.110 – The resolved IPv4 address.

🔁 Reverse Lookup (IP ➡ Domain)
bash
Copy
Edit
nslookup 142.250.71.110
Returns the domain name (PTR record) for that IP.

🐧 2. Using host (Linux, macOS)
📌 Example:
bash
Copy
Edit
host google.com
🔍 Sample Output:
bash
Copy
Edit
google.com has address 142.250.71.110
google.com has IPv6 address 2404:6800:4009:827::200e
google.com mail is handled by 10 smtp.google.com.
✅ What it shows:
A record: google.com has address 142.250.71.110

AAAA record: IPv6 version

MX record: Mail server for the domain

🧠 Summary: nslookup vs host
Feature	nslookup	host
Platforms	Windows, Linux, macOS	Linux, macOS
Usage Style	Interactive & CLI mode	Simple one-line commands
Best for	Detailed DNS diagnostics	Quick lookups
Reverse Lookup	Yes	Yes
MX/NS Records	Yes (set type=MX)	Yes (host -t MX domain.com)

⚡ Example Usage Recap
Task	nslookup	host
A record	nslookup google.com	host google.com
MX record	nslookup -type=MX gmail.com	host -t MX gmail.com
Reverse IP	nslookup 8.8.8.8	host 8.8.8.8



✅ Quick Summary
Feature	                  dig	                                   nslookup
Full Name	Domain Information Groper	Name Server Lookup
Platforms	Linux, macOS (installable on Windows)	Windows, macOS, Linux
Output	Detailed, structured, script-friendly	Simpler, human-readable
Advanced DNS Info	Yes (EDNS, flags, TTLs, sections)	Basic (limited protocol details)
Reverse Lookups	        sYes	                                     Yes
Query Types	A, MX, TXT, NS, CNAME, etc.	A, MX, TXT, NS, etc.
Batch Scripting	Ideal (clean format)	Poor (inconsistent formatting)
Interactivity	No interactive mode (one command)	Can be used interactively
Maintenance	Still actively maintained (by ISC)	Deprecated in some systems

🧪 Example Comparison: Lookup A record for google.com
Using dig:
bash
Copy
Edit
dig google.com
Output (partial):

css
Copy
Edit
;; QUESTION SECTION:
;google.com.            IN    A

;; ANSWER SECTION:
google.com.     295    IN    A    142.250.71.110
✅ Shows:

Detailed DNS flags

Query time

Server used

Answer section separated and scriptable

Using nslookup:
bash
Copy
Edit
nslookup google.com
Output:

yaml
Copy
Edit
Server:  192.168.1.1
Address: 192.168.1.1#53

Non-authoritative answer:
Name:    google.com
Address: 142.250.71.110
✅ Simpler output, but:

Less structured

No section headers

Less detail on TTL or flags

🛠️ When to Use What
Use Case	Use dig	Use nslookup
Scripting / Automation	✅ Preferred	❌ Not ideal
Learning DNS details (TTL, flags)	✅ Very informative	❌ Limited info
Quick manual lookup (Windows)	❌ Not installed by default	✅ Built-in
Digging into DNS issues deeply	✅ Best choice	❌ Too basic
Interactive querying	❌ (no interactive shell)	✅ Supports interactive mode






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
booting process of linux:
------------------------
BIOS (Basic input output system)- MBR-GRUB- KERNETL-SYSTEM D PROCESS
mbr- (master boot record)
grub-(grand unified boot loader)
kernel-(OS)
System d process( alll the linux process start up at the time of booting)

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
6. sudo groupadd username groupname
7. sudo gpasswd -a username groupname, To set the group password --gpasswd groupname, 
   To make a user the group's owner- gpasswd -m username groupname

8. r- reasd -4
   w- write 2
   x- execute 2

   user grop others

9. umask 022
   defualt permission in linux system for files -666 folders-777
   if we give umask 022  subtract from default permissions files 644 folders 755

10. zip: zip -r ldf.zip document
                laf.tar 
     -cvzf 
      c-compress
      v-verboze
      z-zip
      f-filename


11. wget and curl are command line tools used for downloading files from remote server.

CURL   
-----
-Supports a wide range of protocols,
including HTTP, HTTPS, FTP, FTPS,
SCP, SFTP, and more.
-Can handle a variety of data formats,
including JSON, XML, and CSV.
-Supports authentication and cookies.
-Can interact with APIs.

WGET
-----
-Supports HTTP and FTP protocols
-Can download recursively to
download all linked files
-Can handle slow or unstable
connections with ease.
-Can resume interrupted downloads.


                                                            Jenkins
=================================================================================================================================

1.Jenkins file is like configuration file.

Example of walmart techstack:
----------------------------------

                                       Walmart Techstack Application
==================================================================================================
|               |            |           |             |              |       |                |
cicd     securitytools   buildtools artifactory  Infractureascode  docker     k8        MonitoringSRE


                   --------> Supplychain
                   |
Microservice-------|------> Transportation
                   |------> Item and Inventory
                   |
                   --------> Purchase order

Multiple CICD tools are using in different Oraganizations--> Jenkins/Bamboo/etc


There are different CICD pipeline in each environment:
-------------------------------------------------------
Dev environment---->CICD
QE  environment------>CICD       }----> Devops Enginer
STAGE environment------>CICD
PROD  environment------->CICD

Advantages of CICD Pipeline
------------------------------
1.Faster delivery
2.quick deployment
3.less chances of error
4.stability
5.reliablity
6.quick bug fixed
7.version controller
8.automations

CICD Architecure:                  
==============  
|--------------------| 
|Code + Jenkinsfile  |
|--------------------|
    |
    |
    |
    |                                                     ----------------Ansibler/Argo CD for CD------------------
____|______________________________________________________________________________________________________________
|           |                |           |              |           |           |           |                    | 
|           |                |           |              |           |           |           |                    |
|           |                |           |              |           |           |           |                    |
|           |                |           |              |           |           |           |                    |
| checkout  | security       | build     | artifactory  |   IAC     | Docker    |    K8     |                    |
|           |                |           |              |           |           |           |                    |
|           |                |           |              |           |           |           |                    |
|           |                |           |              |           |           |           |                    |
|           |                |           |              |           |           |           |                    |
|___________|________________|___________|______________|___________|___________|___________|____________________|

Skeleton
----------
                                                                Image
 git repository code-10gb                                          |
   +                                                               |
  Jenkins file with parameters                                     |
   |                                        Jfrog/Nexus            |
   |                                  (stores binary file)         |
   |                          code-10mb      |(tools)              |
Checkout-----> secrutiy ---> build ---->aritfactory---> IAC---> docker-------------> k8
 (gitclone)       |(tools)      |
                  |             |          |------->Java ----------> POM.XML---> Maven
                checkmarks     maven       | 
                blackduck       |(tools)---|-------> Nodejs/React---> Package.json----> nmp/node
                 sonarqube                 |   
                 fortify                   |-------> android--------->-build.gridle-->gridle
                 owasp                     |------->python---------->req.txt ----->python 
               

Below is  groovy code in Jenkinsfile (configurationfile)
-----------------------------------------------------------
-Two types of Jenkins file, Declarative and scripted file.
-Each of the repository should have jenkins file that will be created by devops engineer.

Syntax of Jenins file:
--------------------------
pipeline{
   agent any{
        environment variables{
              parameters{
                     choice="value=terraform": yes/no
                     string=" 
                     stages{
                          stage{
                               steps{
                                   script{
                                         code in block

Build toos:
================
Java -----> POM.XML---> Maven
Nodejs/React---> Package.json----> npm/node
android--------->build.gridle-->gridle
python--------->req.txt ----->python


https://github.com/praveen1994dec/Java_app_3.0

For Code navagation structure always follows in this https://github.com/praveen1994dec/Java_app_3.0
-----------------------------------------------------
  -Java_app_3.0/src/main/java/com/minikube/sample/
Java_app_3.0/src/main/java/com/minikube/sample/rest/controller/HomeResource.java


POM-ProjectOjbectModel- 
-------------------------
Imp dependencides in Pom.xml ---Output- Arificatid.version.packaging
=============================
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
    <groupId>com.minikube.sample</groupId>--------------------> Application structure
    <artifactId>kubernetes-configmap-reload</artifactId>------>Binary file name
    <version>0.0.1-SNAPSHOT</version>-------------------------->kubernetes-configmap-reload-.0.0.1-SNAPSHOT.jar
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
    |
    |
___Branches______________________________
|    |       |          |       |     |
Dev  QE   Feature    release  prod  hotfix

sprint.month.year.version
2.4.25.1-supplychain

    0.0.1 |2.4.2.5
majorv.minorv.pathv | majorv.minorv.pathv.incrmentalv

Automation4:  How you are updating the versions with the help of shell script in CICD Pipeline
-----------------------------------------------------------------------------------------------

Ex: Here is the prompt in google for stackoverflow code-maven helper plugin to increment the version automatically
-----
There are a couple of popular Maven plugins that accomplish this feat:

Maven Release Plugin
Build Number Maven Plugin
The Maven Release Plugin from the Apache Maven Project is a bit overkill for simply updating the version number. Therefore use the latter plugin to create a version number (in the form of MAJOR.MINOR.BUILD; e.g., 3.1.4 where 4 is auto-incremented) as follows:

Open the project's pom.xml file.
Include the plugin within the build section (after the dependencies section):
  <scm>
    <connection>scm:svn:http://127.0.0.1/dummy</connection>
    <developerConnection>scm:svn:https://127.0.0.1/dummy</developerConnection>
    <tag>HEAD</tag>
    <url>http://127.0.0.1/dummy</url>
  </scm>
  <build>
    <plugins>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>buildnumber-maven-plugin</artifactId>
        <version>1.4</version>
        <executions>
          <execution>
            <id>buildnumber</id>
            <phase>validate</phase>
            <goals>
              <goal>create</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <format>{0,number}</format>
          <items>
            <item>buildNumber</item>
          </items>                    
          <doCheck>false</doCheck>
          <doUpdate>false</doUpdate>
          <revisionOnScmFailure>unknownbuild</revisionOnScmFailure>   
        </configuration>
      </plugin>    
    </plugins>
    <finalName>${project.artifactId}-${project.version}.${buildNumber}</finalName>
  </build>
Ensure that the pom.xml defines the major and minor version in the version element near the top of the file. For example:
<version>3.1</version>
Save the pom.xml file.
Rebuild the project.
The version number should increase.

               (OR)

You can do it with without pom modification with the help of maven plugins and scripting.
======================================================================================================
For example to increment automatically the second digit of a version that doesn't have snapshot as prefix like in your case, on a linux system you can do :

#get the current pom version and store it into a variable
version=$(mvn -q -U -Dexpression=project.version -DforceStdout maven-help-plugin:evaluate)
#increment the second digit of the version and overwrite the variable
version=$(echo ${version} |  awk -F'.' '{print $1"."$2+1"."$3}' |  sed s/[.]$//)
#update the pom with the new version
mvn -U versions:set -DnewVersion=${version}
It works for versions with 3 digits but also 2 digits thanks to the sed.
Of course move the default increment part : "+1" on the digit that suits to your requirements :

# increment the first digit
awk -F'.' '{print $1+1"."$2"."$3}'

# increment the second digit
awk -F'.' '{print $1"."$2+1"."$3}'

# increment the last digit
awk -F'.' '{print $1"."$2"."$3+1}'

Maven Commands: 
================
- Maven only reads pom.xml file
-
1 mvn clean--- Removes the target-jar,binary and dependeciess
2 mvn test --- Runs all the test cases
3 mvn install--- It cleans ,runs the test and install the depndeciess
4 mvn build
5 mvn deploy   - sending to server
6.mvn package--creates a package

1. Validate: This step validates if the project structure is
correct. For example – It checks if all the
dependencies have been downloaded and are
available in the local repository. 
-•mvn clean: Cleans the project and removes all files
generated by the previous build.

2. Compile: It compiles the source code, converts the
.java files to .class, and stores the classes in the
target/classes folder
-•mvn compile: Compiles source code of the project.

3. Test: It runs unit tests for the project
•mvn test-compile: Compiles the test source code.
•mvn test: Runs tests for the project.

4. Package: This step packages the compiled code in a
distributable format like JAR or WAR
•mvn package: Creates JAR or WAR file for the project to
convert it into a distributable format

5. Integration test: It runs the integration tests for the
project.
•mvn install: Deploys the packaged JAR/ WAR file to the
local repository
•mvn site: generate the project documentation.

6. Verify: This step runs checks to verify that the project
is valid and meets the quality standards.
•mvn validate: validate the project’s POM and
configuration.

7•Install: This step installs the packaged code to the
local Maven repository.
•mvn install: Deploys the packaged JAR/ WAR file to the
local repository

8. Deploy: It copies the packaged code to the remote
repository for sharing it with other developers.

mvn idea:idea: generate project files for IntelliJ IDEA or
Eclipse.
•mvn release:perform: Performs a release build.
•mvn deploy: Copies the packaged JAR/ WAR file to the
remote repository after compiling, running tests and
building the project.

 Automation-5: Build------>JFROG Artifactory repository
 ===============

                              -------> Jar
                   (Pom.xml) |
Java ---->Maven--->Target----|
             |                 ------> Binary
             |
             | 

   mvn clean install---- binary---- curl -x put -v username: password -t "k8.jar" "url of jfrog"
                                            get 
                                            post
                                            delete
x: request
u: username
t: target
k8: kubernetes


Here is the Jenkins file:
---------------------------
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



***
Java_app_3.0/Jenkinsfile Latest---- Child library
@Library('my-shared-library') _------- Parent library
****


Automation6 : 1.Write the jenkisnfile with parallel stage of execute tools in devops
---------------------------------------------------------------------------------------------

Certainly! Below is an example of a Jenkins pipeline Jenkinsfile that executes security tools in parallel within a devops pipeline. This can be used for tools such as static code analysis, dependency scanning, container security scanning, etc.

groovy
Copy
pipeline {
    agent any

    environment {
        // Define any environment variables needed for the security tools
        SECURITY_TOOL_A_HOME = '/path/to/toolA'
        SECURITY_TOOL_B_HOME = '/path/to/toolB'
        SECURITY_TOOL_C_HOME = '/path/to/toolC'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the code from version control
                    checkout scm
                }
            }
        }

        stage('Run Security Tools in Parallel') {
            parallel {
                stage('Static Code Analysis') {
                    steps {
                        script {
                            // Example: Run a static code analysis tool (e.g., SonarQube)
                            echo 'Running Static Code Analysis...'
                            sh "${SECURITY_TOOL_A_HOME}/bin/sonar-scanner"
                        }
                    }
                }

                stage('Dependency Scanning') {
                    steps {
                        script {
                            // Example: Run a dependency scanning tool (e.g., OWASP Dependency-Check)
                            echo 'Running Dependency Scanning...'
                            sh "${SECURITY_TOOL_B_HOME}/bin/dependency-check.sh"
                        }
                    }
                }

                stage('Container Security Scan') {
                    steps {
                        script {
                            // Example: Run a container security scan tool (e.g., Trivy)
                            echo 'Running Container Security Scan...'
                            sh "trivy --no-progress --exit-code 1 --severity HIGH,CRITICAL --quiet ${WORKSPACE}/docker-image"
                        }
                    }
                }

                stage('SAST - Static Application Security Testing') {
                    steps {
                        script {
                            // Example: Run SAST tool (e.g., Checkmarx)
                            echo 'Running SAST Scan...'
                            sh "${SECURITY_TOOL_C_HOME}/bin/checkmarx.sh"
                        }
                    }
                }
            }
        }

        stage('Quality Gate') {
            steps {
                script {
                    // Example: Perform some post-scan quality check (e.g., check SonarQube quality gate)
                    echo 'Checking Quality Gate...'
                    // Insert logic to check SonarQube or any other tool's quality gate status
                }
            }
        }
    }

    post {
        success {
            echo 'Security scans completed successfully.'
        }

        failure {
            echo 'Security scans failed, investigate the logs.'
        }

        always {
            echo 'Cleaning up resources...'
            // Clean up any resources, containers, etc. if needed.
        }
    }
}
Explanation:
Checkout: First, we checkout the code from your version control (Git).
Run Security Tools in Parallel:
The parallel block allows the execution of different security tools concurrently to speed up the pipeline.
Each security tool (static code analysis, dependency scanning, container security, and SAST) is run in a separate stage.
For example:
Static Code Analysis might be SonarQube or any other static analysis tool.
Dependency Scanning might use OWASP Dependency-Check or similar.
Container Security Scan could use tools like Trivy, Anchore, or Clair.
SAST (Static Application Security Testing) could use tools like Checkmarx or Fortify.
Quality Gate: You can use this stage to check the results of your security tools (e.g., SonarQube Quality Gate or similar).
Post Actions: After the pipeline runs, you can handle success, failure, or cleanup.
You can adjust the security tools and scanning configurations as per your needs.

Key Notes:
Ensure you have the appropriate security tools installed on your Jenkins agents or containers.
Set proper environment variables or secrets for the tools if required.
Parallel execution speeds up the scanning process, but be mindful of your system's capacity to run multiple tools simultaneously.


2.How to write the jenkinsfile for the environement variables
----------------------------------------------------------------

In Jenkins, you can define environment variables in a Jenkinsfile in several ways, depending on your needs. Here are the main methods for defining environment variables and some common use cases:

1. Environment Block (Global Environment Variables)
You can define environment variables globally for the entire pipeline using the environment block at the top of the pipeline.

groovy
Copy
pipeline {
    agent any

    environment {
        MY_GLOBAL_VAR = 'some_value'
        ANOTHER_VAR = 'another_value'
        MY_SECRET = credentials('my-secret-id') // Using Jenkins credentials plugin to securely handle secrets
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "MY_GLOBAL_VAR is: ${MY_GLOBAL_VAR}"
                    echo "ANOTHER_VAR is: ${ANOTHER_VAR}"
                    // Using the secret environment variable
                    echo "Secret: ${MY_SECRET}"
                }
            }
        }
    }
}
Global Scope: Environment variables defined here are available throughout the pipeline, including all stages and steps.
Using Jenkins Credentials: If you're using secrets (like API keys, passwords, etc.), you can store them in Jenkins Credentials and access them using the credentials() function, as shown above with MY_SECRET.
2. Environment Variables for Specific Stages

You can also define environment variables that only apply to specific stages. This is useful when you need different variables or values for each stage.

groovy
Copy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            environment {
                CHECKOUT_DIR = '/path/to/checkout'
            }
            steps {
                echo "Checking out code to directory: ${CHECKOUT_DIR}"
                checkout scm
            }
        }

        stage('Build') {
            environment {
                BUILD_DIR = '/path/to/build'
            }
            steps {
                echo "Building in directory: ${BUILD_DIR}"
                // Build logic here
            }
        }

        stage('Test') {
            environment {
                TEST_DIR = '/path/to/test'
            }
            steps {
                echo "Running tests in directory: ${TEST_DIR}"
                // Test logic here
            }
        }
    }
}
Stage-Specific Environment Variables: These variables are only available inside the stage where they are defined. Other stages won’t have access to them.

3. Environment Variables in Script Blocks

You can also set environment variables directly within a script block or within individual sh steps. This is especially useful for temporary variables or when you need to modify the environment within a shell command.

groovy
Copy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Defining environment variable within the script block
                    def buildVersion = "1.0.0"
                    echo "Building version: ${buildVersion}"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Set environment variables for shell commands
                    def deployDir = "/deploy/${BUILD_VERSION}"
                    sh """
                        echo "Deploying to: ${deployDir}"
                        # Actual deploy command here
                    """
                }
            }
        }
    }
}
Script-Level Variables: This allows you to define variables at a more granular level within a stage or script block.
4. Environment Variables via Jenkinsfile Parameters
Jenkins also supports parameters that allow users to pass values to a pipeline when it is triggered. These parameters can act as environment variables.

groovy
Copy
pipeline {
    agent any

    parameters {
        string(name: 'APP_VERSION', defaultValue: '1.0.0', description: 'Version of the app to deploy')
        booleanParam(name: 'DEPLOY_TO_PROD', defaultValue: false, description: 'Deploy to production?')
    }

    environment {
        MY_ENV_VAR = 'SomeValue'
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out version: ${params.APP_VERSION}"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building app with version: ${params.APP_VERSION}"
                echo "Deploy to Production: ${params.DEPLOY_TO_PROD ? 'Yes' : 'No'}"
                // Add build logic here
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (params.DEPLOY_TO_PROD) {
                        echo "Deploying to production with version: ${params.APP_VERSION}"
                        // Add deploy logic here
                    } else {
                        echo "Deploying to staging with version: ${params.APP_VERSION}"
                        // Add staging deploy logic here
                    }
                }
            }
        }
    }
}
Using Parameters as Environment Variables: In this case, we are using params.APP_VERSION to dynamically control what version of the app is being built and deployed based on user input when triggering the pipeline.
5. Using Environment Variables in Shell Scripts
In addition to defining environment variables in the Jenkinsfile, you can use them inside shell commands (sh), and they can be exported within the shell script.

groovy
Copy
pipeline {
    agent any

    environment {
        MY_ENV_VAR = 'value_from_jenkinsfile'
    }

    stages {
        stage('Setup') {
            steps {
                script {
                    // Set environment variable dynamically using shell
                    sh '''
                        export MY_LOCAL_VAR="value_from_shell"
                        echo "MY_LOCAL_VAR is: $MY_LOCAL_VAR"
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                echo "MY_ENV_VAR from Jenkinsfile: ${env.MY_ENV_VAR}"
                // Access environment variable within shell script
                sh 'echo "MY_ENV_VAR is: $MY_ENV_VAR"'
            }
        }
    }
}
Using Shell for Variable Definition: You can define variables within shell commands, and export them for use later in the pipeline. Use the env object to access environment variables inside the pipeline.
Best Practices:
Sensitive Data: For secrets (API keys, passwords, etc.), always use the Jenkins Credentials Plugin. This keeps sensitive data secure and avoids hard-coding it in the Jenkinsfile.
Global vs Local: Define environment variables globally if they need to be accessed across multiple stages. If the variable is only needed for a specific stage, define it in that stage to keep your pipeline organized and avoid conflicts.
Avoid Hard-Coding: Try not to hard-code sensitive or configuration data directly in the Jenkinsfile. Use Jenkins credentials or parameterize the values.


3.How to write the jenkins file not  to execute a particular stage
--------------------------------------------------------------------------


In Jenkins, you can control whether a particular stage is executed by using conditions to skip the execution of the stage. This can be achieved in several ways, depending on your use case. Here are a few ways to skip or conditionally execute a stage in a Jenkins pipeline.

1. Using when Block
The when block can be used to conditionally control whether a stage is executed or not based on a condition, such as a parameter, environment variable, or any custom logic.

Example: Skip a Stage Based on a Parameter
groovy
Copy
pipeline {
    agent any

    parameters {
        booleanParam(name: 'SKIP_TESTS', defaultValue: false, description: 'Skip tests stage?')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Test') {
            when {
                expression {
                    return !params.SKIP_TESTS
                }
            }
            steps {
                echo 'Running tests...'
                // Add test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment steps here
            }
        }
    }
}
when Block: In this example, the Test stage will be skipped if the SKIP_TESTS parameter is set to true.
Condition: The condition when { expression { return !params.SKIP_TESTS } } ensures that the test stage is skipped if the parameter SKIP_TESTS is true.
2. Using skip Condition in script Block
You can also use a script block with a condition to determine whether or not to run the steps in a stage. If you want to skip the entire stage, you can simply use return to exit from the stage early.

Example: Skip a Stage Based on a Variable
groovy
Copy
pipeline {
    agent any

    environment {
        SKIP_DEPLOY = true // Example condition to skip deploy
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Deploy') {
            steps {
                script {
                    if (env.SKIP_DEPLOY == 'true') {
                        echo 'Skipping deployment.'
                        return // Skip this stage
                    }
                    echo 'Deploying the application...'
                    // Add deploy steps here
                }
            }
        }
    }
}
Skipping a Stage Using return: If SKIP_DEPLOY is true, the Deploy stage will not execute the deployment steps, effectively skipping the stage.
3. Using input to Manually Skip a Stage
You can use the input step to pause the pipeline and ask the user whether to continue or not, which could be used to skip a stage manually.

Example: Skip Stage with User Input
groovy
Copy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Test') {
            steps {
                input message: 'Do you want to run tests?', ok: 'Yes', parameters: [booleanParam(defaultValue: true, description: 'Run tests?', name: 'RunTests')]
                script {
                    if (params.RunTests) {
                        echo 'Running tests...'
                        // Add test steps here
                    } else {
                        echo 'Skipping tests...'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deploy steps here
            }
        }
    }
}
input Step: This will pause the pipeline and ask the user whether to run the tests. If the user selects "Yes," the tests will run. If they select "No," the tests are skipped.
4. Using catchError to Skip Failures
You can use the catchError step to catch failures in a particular stage and decide whether or not to fail the pipeline or skip the failure.

Example: Skip a Stage on Failure
groovy
Copy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Test') {
            steps {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    echo 'Running tests...'
                    // Simulate a failure in tests
                    sh 'exit 1'  // This will fail the tests but will not fail the pipeline due to catchError
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deploy steps here
            }
        }
    }
}
catchError: The catchError step allows you to catch the failure of a stage and proceed with the pipeline without failing the entire job. You can also decide to continue even when the tests fail.
5. Using return in a Stage to Skip Execution
You can simply use return to skip the execution of the stage in a script block if the condition is met.

Example: Skip a Stage Based on Condition
groovy
Copy
pipeline {
    agent any

    environment {
        SHOULD_SKIP_STAGE = true // Example condition to skip stage
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                script {
                    if (env.SHOULD_SKIP_STAGE == 'true') {
                        echo 'Skipping the Test stage.'
                        return // Skip the rest of the stage
                    }
                    echo 'Running tests...'
                    // Test execution logic here
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deploy logic here
            }
        }
    }
}
Key Points:
when Block: This is a powerful way to conditionally skip a stage based on parameters or environment variables.
input Step: Use it to ask the user manually whether they want to skip a stage.
catchError: Useful for skipping stages based on errors or failures without failing the pipeline.
script Block with return: Use return to exit early from a stage, effectively skipping it.



Jenins Document Theory:
-----------------------------
1. Declarative Pipeline Example
The Declarative Pipeline syntax is more structured and user-friendly, making it ideal for simple pipelines. It follows a predefined structure and is best for simpler workflows.

Example: Declarative Pipeline
groovy
Copy
pipeline {
    agent any

    environment {
        // Define environment variables that are available throughout the pipeline
        BUILD_ENV = 'production'
        DEPLOY_ENV = 'staging'
    }

    parameters {
        string(name: 'APP_VERSION', defaultValue: '1.0.0', description: 'Version of the app to deploy')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run Tests?')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building version ${params.APP_VERSION} for ${env.BUILD_ENV} environment"
                // Add build steps (e.g., mvn, npm, etc.)
            }
        }

        stage('Test') {
            when {
                expression {
                    return params.RUN_TESTS
                }
            }
            steps {
                echo 'Running tests...'
                // Add test steps here (e.g., `npm test`, `mvn test`, etc.)
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${params.APP_VERSION} to ${env.DEPLOY_ENV} environment"
                // Add deployment steps here (e.g., AWS CLI, Kubernetes, etc.)
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
        always {
            echo 'Cleaning up resources...'
            // Add cleanup steps, such as removing temporary files, stopping containers, etc.
        }
    }
}
Key Points of the Declarative Pipeline:
Structured: The pipeline is more structured, making it easier to read and write.
Environment Variables: Defined globally in the environment block.
Parameters: Parameters are defined in the parameters block for user input.
when Block: The when block is used to conditionally execute the Test stage based on the RUN_TESTS parameter.
Post Actions: post block is used to define actions that run after the pipeline completes, whether it’s successful, failed, or always.
2. Scripted Pipeline Example
The Scripted Pipeline is more flexible but requires more complex syntax. It allows you to write the pipeline with full control over how it behaves.

Example: Scripted Pipeline
groovy
Copy
node {
    try {
        // Define environment variables
        def buildEnv = 'production'
        def deployEnv = 'staging'
        def appVersion = '1.0.0'

        // Input Parameters
        def runTests = input(
            message: 'Do you want to run tests?',
            parameters: [
                booleanParam(defaultValue: true, description: 'Run tests?', name: 'RUN_TESTS')
            ]
        )

        // Checkout code from SCM
        stage('Checkout') {
            echo 'Checking out the source code'
            checkout scm
        }

        // Build Stage
        stage('Build') {
            echo "Building version ${appVersion} for ${buildEnv} environment"
            // Add your build logic here (e.g., compile code, package, etc.)
        }

        // Test Stage
        if (runTests) {
            stage('Test') {
                echo 'Running tests...'
                // Add your testing logic here (e.g., `npm test`, `mvn test`, etc.)
            }
        } else {
            echo 'Skipping tests as per user input.'
        }

        // Deploy Stage
        stage('Deploy') {
            echo "Deploying version ${appVersion} to ${deployEnv} environment"
            // Add your deployment logic here (e.g., AWS CLI, Kubernetes, etc.)
        }

    } catch (Exception e) {
        // Handle failure
        currentBuild.result = 'FAILURE'
        throw e
    } finally {
        // This will always execute regardless of success or failure
        echo 'Cleaning up resources...'
        // Add any cleanup steps (e.g., delete temporary files, stop containers)
    }
}
Key Points of the Scripted Pipeline:
Flexibility: The scripted pipeline gives you more flexibility and control because it allows you to write Groovy code directly. It’s best for complex use cases.
Node Block: The entire pipeline is wrapped in a node block, meaning it runs on a Jenkins agent. You must define the node block at the beginning.
Try-Catch: A try-catch block is used to handle errors gracefully and mark the build as failed if an exception occurs.
Conditional Logic: The pipeline logic is written in Groovy, so you have complete control over the flow, such as skipping a stage based on the user’s input (runTests).
Post Actions: A finally block is used for cleanup, ensuring that cleanup happens no matter what (success or failure).
Comparison of Declarative vs Scripted Pipelines
Feature	Declarative Pipeline	Scripted Pipeline
Syntax	More structured and easier to read and write	More flexible, allows complex logic using Groovy
Control	Limited control over pipeline execution flow	Full control over the execution flow
Flexibility	Less flexible, good for standard pipelines	More flexible, ideal for complex pipelines
Declarative Features	Easy to define environment variables, parameters, and conditions	Not required, can be done using regular Groovy code
Error Handling	Handled with post section	Can use try-catch for more fine-grained error handling
Use Cases	Best for simpler, standard use cases	Best for complex, dynamic use cases
When to Use Each:
Declarative Pipeline: Ideal for simpler, more standard use cases where you don’t need complex control flow and prefer a structured, easy-to-read format.
Scripted Pipeline: Ideal for more complex pipelines where you need fine-grained control over the pipeline execution, such as dynamic behavior based on inputs or advanced error handling.
Both pipeline types can achieve the same outcomes, but Declarative Pipelines are often favored for ease of use and clarity, while Scripted Pipelines provide the flexibility needed for more complex workflows.
Assignment-1  Write the groovy code to send jarfile to jfrog repo
Assignment -2 Different jenkins file scenarios



2.Pipeline - A pipeline is a set of instructions that includes the processes of continuous delivery. For example, creating an application,
testing it, and deploying the same. Moreover, it is a critical element in declarative pipeline syntax, which is a collection of all stages in
a Jenkinsfile. We declare different stages and steps in this block.
• pipeline{ } Node - A node is a key element in scripted pipeline syntax. Moreover, it acts as a machine in Jenkins that executes the
Pipeline.
• node{ } Stage - A stage consists of a set of processes that the Pipeline executes. Additionally, the tasks are divided in each stage,
implying that there can be multiple stages within a Pipeline. The below snippet shows the different stages that one can define in a
Pipeline.
• Steps - A step in Jenkins defines what we have to do at a particular step in the process. There can be a series of steps within the stage.
Moreover, whatever step we define in a stage would be executed within it.
• Agent - An agent is a directive that enables the users to execute multiple projects within the same Jenkins instance by distributing the
load. Moreover, we assign an executor to the build through an agent. You can either use a single agent for the entire pipeline or use a
distinct agent for the different stages of the pipeline. Subsequently, some of the parameters used with agents are -
• Any- Any of the available agents execute the pipeline.
• None- It is used at the pipeline root and implies no global agent, but each stage must specify its own agent.
• Label- The labeled agent is used to execute the pipeline or the specific stage.
• Docker- One can use the Docker images as the execution environment & specifying the agent as docker.


Merge Request from dev to master Branch:
---------------------------------------------------
Child Pipeline -
=================
DevTeam  Code Commit  To GitHub  Triggers Child Pipeline (WebHook) 
Sonar/Blackduck/Fortify(Stage 1 - In Parallel)  Creates the Merge
Request(Stage 2 – Sends Email to Approver)
Master Pipeline -
==================
Merge request gets approved  Master Pipeline Trigger(WebHook) 
Sonar/Blackduck/Fortify(Stage 1 - In Parallel)  Build Code (Maven)  Artifact
Push (Jfrog)  Pull Artifact(Ansible)  Deployment to QA(OnPrem/Cloud) 
Performance testing/Integration testing  Deployment to Syage  Send
Notification via Email


Webhook Setup
• In your project or group, on the left sidebar, select Settings > Webhooks.
• In URL, enter the URL of the webhook endpoint.
• In Secret token, enter the secret token to validate payloads.
• In the Trigger section, select the events to trigger the webhook






JSL( Jenkins shared Libary)
-------------------------------
***
Java_app_3.0/Jenkinsfile Latest---- Child library
@Library('my-shared-library') _------- Parent library
****

Path -Java_app_3.0/Jenkinsfile(Parent)---vars---different use cases using groovy code

Assignment-1
Write the the groovy code to send the jar file to the jfrog
-------------------------------------------------------------



Jenkins Server installation:
========================================
  |                           |
ubuntu                       centos 
-------                    ---------

1.yum/apt
2.packages
3.rpm packages- (red hat package manager)
4.docker images/container
5.curl / linux commands
6.k8 pods

Automations with jenkins
==============================

1. Write a shell script to install the jenkins on linux server
2. Write a groovy script where the two jobs are dependent of each other
3. Write a groovy script for different jenkins scenarios


4.Write a jenkinsfile where the one stage variables are passed to other stage by using rest api automation script
===================================================================================================================
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



Remote Access API 
Jenkins provides machine-consumable remote access API to its functionalities. Currently it comes in three flavors:

XML

JSON with JSONP support

Python

Remote access API is offered in a REST-like style. That is, there is no single entry point for all features, and instead they are available under the ".../api/" URL where "..." portion is the data that it acts on.

For example, if your Jenkins installation sits at https://ci.jenkins.io, visiting https://ci.jenkins.io/api/ will show just the top-level API features available – primarily a listing of the configured jobs for this Jenkins controller.
Or if you want to access information about a particular build, e.g. https://ci.jenkins.io/job/Websites/job/jenkins.io/job/master/lastSuccessfulBuild/ , then go to https://ci.jenkins.io/job/Websites/job/jenkins.io/job/master/lastSuccessfulBuild/api/ and you’ll see the list of functionalities for that build.

What can you do with it?
Remote API can be used to do things like these:

retrieve information from Jenkins for programmatic consumption.

trigger a new build

create/copy jobs

Submitting jobs
Jobs without parameters

You merely need to perform an HTTP POST on JENKINS_URL/job/JOBNAME/build.

This also works for Multibranch Pipelines and Organization Folders. It would trigger a scan.

Jobs with parameters

Simple example - sending "String Parameters":

curl JENKINS_URL/job/JOB_NAME/buildWithParameters \
  --user USER:TOKEN \
  --data id=123 --data verbosity=high
Another example - sending a "File Parameter":

curl JENKINS_URL/job/JOB_NAME/buildWithParameters \
  --user USER:PASSWORD \
  --form FILE_LOCATION_AS_SET_IN_JENKINS=@PATH_TO_FILE
The symbol '@' is important in this example. Also, the path to the file is absolute path. In order to make this command work, you need to configure your Jenkins job to take a file parameter and match the File location field in the Jenkins job configuration with the key in the --form option.


Jenkins rest api to get the agent details:
--------------------------------------------
https://<JENKINS_HOST>/job/MY_JOB/api/json?fetchAllbuildDetails=True



basic syntax
===============
https://<JENKINS_HOST>/job/MY_JOB/api/json?fetchALLbuildDetails=True



Master Slave Architecture:
==============================
                       -------- slave/agent/node
                      | (jarfile)
                      |
Master ---------------| (jarfile)
                       -------- slave/agent/node
(Jenkins)



***Project1:******
=============================
1.Jenkins server-name and region us-east-1
2.ubuntu-server
3.t2.medium
4.storage - 25gb
5.launch instance
6.sudo su
7. 
sudo apt update -y

sudo apt upgrade -y 
sudo apt install openjdk-17-jre -y

8.

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update -y 
sudo apt-get install jenkins -y

9. security -->security groups----> edit inbound rules--> type- all traffice && source anywhere IPV4
9.1 Take iP address:8080 in the browser 
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
16. build now in jenkins and check the console outputs you will get error as shared lib not found.

17. Go to mange jenkins----configure system-- global pipeline library (global trusted pipeline  libraries

    Name--->my-shared-library
    Defaultversion-->main
    git-https://github.com/praveen1994dec/jenkins_shared_lib.git
    save and apply

18. Build
19. /etc/apt/sources.list.d# cd /var/lib/jenkins/
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


=======================================================
Assigments -1

==========================
✅ Assignment 1 – JFrog Setup & Manual Upload
===========================

🎯 Goal: Set up JFrog Artifactory on an EC2 instance and manually upload a Maven-built JAR file.

---------------------------------
🖥️ EC2 Configuration
---------------------------------
- Launch EC2 Instance (Ubuntu)
- Instance Type: t2.medium (recommended) or t2.micro with 8GB EBS
- Open ports in Security Group:
    - TCP 22 (SSH)
    - TCP 8081 (JFrog UI)
    - TCP 8082 (JFrog Repo upload)

---------------------------------
🧱 Step-by-Step
---------------------------------

1. Install Docker
---------------------
curl -s https://raw.githubusercontent.com/praveen1994dec/tools_installation_scripts/main/docker.sh | bash

2. Install JFrog Artifactory
---------------------
curl -s https://raw.githubusercontent.com/praveen1994dec/tools_installation_scripts/main/Jfrog.sh | bash

3. Access JFrog UI
---------------------
URL: http://<EC2-IP>:8081/artifactory
Login: admin
Password: password

4. Install Maven
---------------------
curl -s https://raw.githubusercontent.com/praveen1994dec/tools_installation_scripts/main/Maven.sh | bash

5. Install Git
---------------------
sudo apt update
sudo apt install -y git
git --version

6. Clone Java App Repository
---------------------
git clone https://github.com/praveen1994dec/Java_app_3.0.git
cd Java_app_3.0

7. Build Java App Using Maven
---------------------
mvn clean install -DskipTests

8. Go to the `target` folder
---------------------
cd target
# Locate JAR: kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar

9. Upload JAR to JFrog Repo
---------------------
curl -X PUT -u admin:password -T kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar http://<EC2-IP>:8082/artifactory/example-repo-local/

---------------------------------
✅ Expected Output:
JAR file successfully uploaded to JFrog at:
http://<EC2-IP>:8081/artifactory/example-repo-local/




===========================
✅ Assignment 3 – Jenkins Pipeline with JFrog Upload
===========================

🎯 Goal: Automate the upload of the JAR file to JFrog Artifactory within a Jenkins pipeline.

📂 File to Modify: Jenkinsfile in Java_app_3.0 repo

---------------------------------
🧱 Add This Stage AFTER Maven Build
---------------------------------

stage('Build and Add Artifact to the repo : JFrog') {
  when { expression { params.action == 'create' } }
  steps {
    script {
      // Artifactory configuration
      def artifactoryUrl = 'http://<EC2-IP>:8081/artifactory'
      def repoName = 'example-repo-local'
      def targetPath = 'kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar'
      def localArtifactPath = '/var/lib/jenkins/.m2/repository/com/minikube/sample/kubernetes-configmap-reload/0.0.1-SNAPSHOT/kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar'
      def apiKeyOrUsername = 'admin'
      def apiKeyOrPassword = 'Password@123'

      // Extract the filename
      def fileName = localArtifactPath.split('/').last()
      def uploadUrl = "${artifactoryUrl}/${repoName}/${targetPath}/${fileName}"

      // Upload using curl
      def uploadCommand = """
      curl -X PUT -u ${apiKeyOrUsername}:${apiKeyOrPassword} -T ${localArtifactPath} ${uploadUrl}
      """

      def uploadResult = sh(script: uploadCommand, returnStatus: true)

      if (uploadResult == 0) {
        echo "Artifact successfully uploaded to Artifactory."
      } else {
        error "Failed to upload artifact to Artifactory. Exit code: ${uploadResult}"
      }
    }
  }
}

====
Example of full code:
@Library('my-shared-library') _

pipeline {

    agent any

    parameters {
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
        string(name: 'ImageName', description: "name of the docker build", defaultValue: 'javapp')
        string(name: 'ImageTag', description: "tag of the docker build", defaultValue: 'v1')
        string(name: 'DockerHubUser', description: "name of the Application", defaultValue: 'praveensingam1994')
    }

    stages {

        stage('Git Checkout') {
            when { expression { params.action == 'create' } }
            steps {
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/praveen1994dec/Java_app_3.0.git"
                )
            }
        }

        stage('Unit Test maven') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    mvnTest()
                }
            }
        }

        stage('Integration Test maven') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    mvnIntegrationTest()
                }
            }
        }

        stage('Static code analysis: Sonarqube') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    def SonarQubecredentialsId = 'sonarqube-api'
                    statiCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }

        stage('Quality Gate Status Check : Sonarqube') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    def SonarQubecredentialsId = 'sonarqube-api'
                    QualityGateStatus(SonarQubecredentialsId)
                }
            }
        }

        stage('Maven Build : maven') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    mvnBuild()
                }
            }
        }

        // 📦 New JFrog Upload Stage Inserted Here
        stage('Build and Add Artifact to the repo : JFrog') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    // Artifactory configuration
                    def artifactoryUrl = 'http://<EC2-IP>:8081/artifactory'
                    def repoName = 'example-repo-local'
                    def targetPath = 'kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar'
                    def localArtifactPath = '/var/lib/jenkins/.m2/repository/com/minikube/sample/kubernetes-configmap-reload/0.0.1-SNAPSHOT/kubernetes-configmap-reload-0.0.1-SNAPSHOT.jar'
                    def apiKeyOrUsername = 'admin'
                    def apiKeyOrPassword = 'Password@123'

                    // Extract the filename
                    def fileName = localArtifactPath.split('/').last()
                    def uploadUrl = "${artifactoryUrl}/${repoName}/${targetPath}/${fileName}"

                    // Upload using curl
                    def uploadCommand = """
                    curl -X PUT -u ${apiKeyOrUsername}:${apiKeyOrPassword} -T ${localArtifactPath} ${uploadUrl}
                    """.stripIndent()

                    def uploadResult = sh(script: uploadCommand, returnStatus: true)

                    if (uploadResult == 0) {
                        echo "Artifact successfully uploaded to Artifactory."
                    } else {
                        error "Failed to upload artifact to Artifactory. Exit code: ${uploadResult}"
                    }
                }
            }
        }

        stage('Docker Image Build') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    dockerBuild("${params.ImageName}", "${params.ImageTag}", "${params.DockerHubUser}")
                }
            }
        }

        stage('Docker Image Scan: trivy') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    dockerImageScan("${params.ImageName}", "${params.ImageTag}", "${params.DockerHubUser}")
                }
            }
        }

        stage('Docker Image Push : DockerHub') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    dockerImagePush("${params.ImageName}", "${params.ImageTag}", "${params.DockerHubUser}")
                }
            }
        }

        stage('Docker Image Cleanup : DockerHub') {
            when { expression { params.action == 'create' } }
            steps {
                script {
                    dockerImageCleanup("${params.ImageName}", "${params.ImageTag}", "${params.DockerHubUser}")
                }
            }
        }
    }
}



This is the parent shared library 

https://github.com/praveen1994dec/jenkins_shared_lib/blob/main/vars/gitCheckout.groovy

========
---------------------------------
📝 Notes:
- Replace <EC2-IP> with your JFrog EC2 instance IP.
- Replace password if it’s different.
- Ensure Jenkins has permission to access localArtifactPath.

✅ Expected Output:
Jenkins uploads the JAR to your Artifactory repository automatically after the Maven build.

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

https://github.com/praveen1994dec/Java_app_3.0/blob/main/Dockerfile

Example docker file:
---------------------
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY ./target/*.jar /app.jar
CMD ["java", "-jar", "/app.jar"]


----
FROM openjdk:8-jdk-alpine

# Accept a JAR filename and app port as build args
ARG JAR_FILE=target/app.jar
ARG APP_PORT=8080

# Set them as environment variables (optional, for runtime use)
ENV APP_PORT=$APP_PORT

# Set working directory
WORKDIR /app

# Copy the specified jar file into the container
COPY ${JAR_FILE} app.jar

# Expose the specified port
EXPOSE ${APP_PORT}

# Run the app
CMD ["java", "-jar", "app.jar"]


🏗 How to Build the Image:
bash
Copy
Edit
docker build \
  --build-arg JAR_FILE=target/my-app-1.0.jar \
  --build-arg APP_PORT=9090 \
  -t my-dynamic-app .


🚀 How to Run the Container:
bash
Copy
Edit
docker run -p 9090:9090 my-dynamic-app

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

Project 2 JFROG setup in docker container: 
-------------------------------------------
Ubuntu
20gb
launch instance


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

##Install in Amazon Ubuntu---https://github.com/praveen1994dec/tools_installation_scripts
sudo usermod -aG docker $USER
docker pull docker.bintray.io/jfrog/artifactory-oss:latest
docker images
sudo mkdir -p /jfrog/artifactory
sudo chown -R 1030 /jfrog/
docker run --name artifactory -d -p 8081:8081 -p 8082:8082 -v /jfrog/artifactory:/var/opt/jfrog/artifactory docker.bintray.io/jfrog/artifactory-oss:latest

now in the security grou change ito alltrafic ip4 and check with the IP address 


Disadvantages of dockercompose
---------------------------
1. No security
2. Multi architecture format
3. Maintenance of docker containers
4. No dashboard
5. No proper rollback
6. No proper deployment strategy
7. No autoscaling/auto healing

Docker compose file
--------------------
services:
   db:
      image: mysql:5.7
      volumes:
        -db_data:C:/Users/User/Desktip/dcompose
      restart: always
      environment:
        MYSQL_ROOT_PASSWORD: rootwordpress
        MYSQL_DATABASE: wordpress
        MYSQL_USER: wordpress
        MYSQL_PASWWORD: wordpress

    wordpress:
      depends_on:
        - db
      image: wordpress:latest
      ports:
        - "8000:80"
      restart: always
      environemnt:
        WORDPRESS_DB_HOST: db:3306
        WORDPRESS_DB_USER: wordpress
        WORDPRESS_DB_PASSWORD: wordpress
volumes:
    db_Data:
======================================================
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
--

def call(String project, String ImageTag, String hubUser){
    
    sh """
     docker image build -t ${hubUser}/${project}:latest .
    """
}

// def call(String aws_account_id, String region, String ecr_repoName){
    
//     sh """
//      docker build -t ${ecr_repoName} .
//      docker tag ${ecr_repoName}:latest ${aws_account_id}.dkr.ecr.${region}.amazonaws.com/${ecr_repoName}:latest
//     """
// }

def call(String project, String ImageTag, String hubUser){
    
    sh """
     docker rmi ${hubUser}/${project}:latest
    """
}

// def call(String aws_account_id, String region, String ecr_repoName){
    
//     sh """
//      docker rmi ${ecr_repoName}:latest ${aws_account_id}.dkr.ecr.${region}.amazonaws.com/${ecr_repoName}:latest
//     """
// }


def call(String project, String ImageTag, String hubUser){
    withCredentials([usernamePassword(
            credentialsId: "docker",
            usernameVariable: "USER",
            passwordVariable: "PASS"
    )]) {
        sh "docker login -u '$USER' -p '$PASS'"
    }
    //sh "docker image push ${hubUser}/${project}:${ImageTag}"
    sh "docker image push ${hubUser}/${project}:latest"   
}


// def call(String aws_account_id, String region, String ecr_repoName){
    
//     sh """
//      aws ecr get-login-password --region ${region} | docker login --username AWS --password-stdin ${aws_account_id}.dkr.ecr.${region}.amazonaws.com
//      docker push ${aws_account_id}.dkr.ecr.${region}.amazonaws.com/${ecr_repoName}:latest
//     """
// }



def call(String project, String ImageTag, String hubUser){
    
    sh """   
     trivy image ${hubUser}/${project}:latest > scan.txt
     cat scan.txt
    """
}

// def call(String aws_account_id, String region, String ecr_repoName){
    
//     sh """
//     trivy image ${aws_account_id}.dkr.ecr.${region}.amazonaws.com/${ecr_repoName}:latest > scan.txt
//     cat scan.txt
//     """
// }
===================================================
                                Kubernetes K8 
==============================================================================================================

         image
.jar--------------->Dockercontainers---------------> Kubernetes


Architecture of Kubernetes
----------------------------------
yaml
|
|
 --
   |
   |  --
   | Master                                                    Slave/Node
 ------------------------                                    -------------------------
 |               
1|->     API SERVER------>>---------->>---------->>------------->>cublet(agent)--8 [Primary component in workernode which talks with API
           ^  7                                                 >> PODS  -- POD  9  [Second compoent in entire
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
           |                                                            --  namespace
                                                                        -- istio
2|->    ETCD 6(It stores all the data in kub)                     >>Kube Proxy  10 [Thrid componenet
 |        ^                                                        (d means distributed database)Continer d or Container Runtime
 |        |(it stores the data in key: value format)
3|-->   Control Manager   5< --<--------<--------- |
 |     CPU                                         ^
 |    - Node controller                            |  
 |    - Replication controller                     ^
 |    - Network controller                         |
4|-->    Scheduler---------------------------------
        (Control manager process the datat and sends to scheduler
          it will schedule the data in worker node)

         image
.jar--------------->Dockercontainers---------------> Kubernetes

States of POD:
------------------------
-----> Troubleshooting of K8
  | -->   Running---- sucess state
  | -->   Crashloopback-- any issues in appplication
  | -->   Pending--- if pod is not able to get data
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


Project 3: EKS Project
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
11. curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
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
19. curl -o kubectl https://amazon-eks.s3.us-west-2.amazon.aws.com/1.20.4/2021-04-12/bin/linux/amd64/kubecctl
20. chmod +x ./kubectl
21. mkdir -p $HOME/bin
22. cp ./kubectl $HOME/bin/kubectl 
23. export PATH=$HOME/bin:$PATH
24. echo 'export PATH=$HOME/bin:$PATH'>>~/.bashrc
25. source $HOME/.bashrc
26 kubectl version --short -client

27. git clone https://github.com/praveen1994dec/kubernetes_java_deployment.git
28. 

STEP 5 – IMPORTANT STEP [ 3 SERVICES IN PROJECT ]
[ Give your dockerhub ID in place of ]
cd shopfront/
mvn clean install -DskipTests
docker build -t /shopfront:latest . 
docker push /shopfront:latest

[ Give your dockerhub ID in place of ]
cd productcatalogue/
mvn clean install -DskipTests
docker build -t praveensingam1994/productcatalogue:latest . 
docker push praveensingam1994/productcatalogue:latest

[ Give your dockerhub ID in place of ]
cd stockmanager/
mvn clean install -DskipTests
docker build -t praveensingam1994/stockmanager:latest . docker push praveensingam1994/stockmanager:latest
 SERVICE1
 praveensingam1994
 praveensingam1994
 praveensingam1994
praveensingam1994
 SERVICE2
  SERVICE3
 praveensingam1994
  STEP 6 - GO TO KUBERNETES FOLDER IN SAME PROJECT
cd kubernetes
kubectl apply -f shopfront-service.yaml kubectl apply -f productcatalogue-service.yaml kubectl apply -f stockmanager-service.yaml
STEP 7 – kubectl get pods
STEP 8 – Hit the below command to start the kubernetes dashboard in EC2
/usr/local/bin/minikube dashboard
STEP9[INNEWEC2WINDOW] -
Open the EC2 in new window and set the PROXY kubectl proxy --address='0.0.0.0' --accept-hosts='^*$'
    
  STEP 9 - Hit in browser to view the dashboard
http://<EC2-IP>:8001/api/v1/namespaces/kubernetes-da shboard/services/http:kubernetes-dashboard:/proxy/#/po d?namespace=default
    [YOU WILL SEE YOUR APPS]
STEP 10 – Hit the below command for each service in
different console of EC2
[ EC2 LOGIN FIRST ]
kubectl port-forward --address 0.0.0.0 svc/shopfront 8080:8010
[EC2 LOGIN FIRST]
kubectl port-forward --address 0.0.0.0 svc/productcatalogue 8090:8020
[ EC2 LOGIN FIRST ]
 
 kubectl port-forward --address 0.0.0.0 svc/stockmanager 9008:8030
STEP 11 –
- http://<EC2IP>:8090/products
- [{"id":"1","name":"Widget","descriptio
   n":"Premium ACME
   Widgets","price":1.1999999999999999555
   910790149937383830547332763671875},{"i
   d":"2","name":"Sprocket","description"
   :"Grade B
   sprockets","price":4.09999999999999964
   47286321199499070644378662109375},{"id
   ":"3","name":"Anvil","description":"La
   rge
   Anvils","price":45.5},{"id":"4","name"
   :"Cogs","description":"Grade Y
   cogs","price":1.8000000000000000444089
   209850062616169452667236328125},{"id":
   "5","name":"Multitool","description":"
   Multitools","price":154.09999999999999
   4315658113919198513031005859375}]
- http://<EC2IP>:9008/stocks
- [{"productId":"1","sku":"12345678","am ountAvailable":5},{"productId":"2","sk u":"34567890","amountAvailable":2},{"p roductId":"3","sku":"54326745","amount Available":999},{"productId":"4","sku" :"93847614","amountAvailable":0},{"pro
   
ductId":"5","sku":"11856388","amountAv
   ailable":1}]
STEP 12 – ANALYZE THE DASHBOARD
[ IGNORE THE ERROR IN 1 POD, It is due to PROBES as
discussed in class ]
 GO TO EACH SEGMENT ON LEFT HAND SIDE AND EXPLORE ☺☺



kubernetes_java_deployment/kubernetes
/productcatalogue-service.yaml

---
apiVersion: v1
kind: Service
metadata:
  name: productcatalogue
  labels:
    app: productcatalogue
spec:
  type: NodePort
  selector:
    app: productcatalogue
  ports:
  - protocol: TCP
    port: 8020
    name: http

---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: productcatalogue
spec:
  selector:
    matchLabels:
      app: productcatalogue
  replicas: 1
  template:
    metadata:
      labels:
        app: productcatalogue
    spec:
      containers:
      - name: productcatalogue
        image: praveensingam1994/productcatalogue:latest
        ports:
        - containerPort: 8020
        livenessProbe:
          httpGet:
            path: /healthcheck
            port: 8025
          initialDelaySeconds: 30
          timeoutSeconds: 1


kubernetes_java_deployment/kubernetes/shopfront-service.yaml

---
apiVersion: v1
kind: Service
metadata:
  name: shopfront
  labels:
    app: shopfront
spec:
  type: NodePort
  selector:
    app: shopfront
  ports:
  - protocol: TCP
    port: 8010
    name: http

---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: shopfront
spec:
  selector:
    matchLabels:
      app: shopfront
  replicas: 1
  template:
    metadata:
      labels:
        app: shopfront
    spec:
      containers:
      - name: shopfront
        image: praveensingam1994/shopfront:latest
        ports:
        - containerPort: 8010
        livenessProbe:
          httpGet:
            path: /health
            port: 8010
          initialDelaySeconds: 30
          timeoutSeconds: 1






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

      /api/v1/namespaces/{namespac3s}/pods
      _________________                            _________________
     |kind: Pod       |                           | kind: Node      |
     |name:           |                           | name:           |
     |   nginx -a     | ---foo                    |      node -1    |
      ------------------       ^                  |-->---------------------
kind:                          |                 |     
  APIService                   |                 ^
  name:                        |                 | 
      FlunderSrv              pods               nodes
apiservices                    ^                 ^
     | (/apis/apiregistrations.|-----------------|         
     | k8s.io/v1/apiservices)          | 
  apiresgistrations.k8s.io/v1        api/v1
     |                                 ^
     |                                 |      
     |_____________<_< ------Build-int resources-->>>----------------apiextentsion.k8s.io/v1---crds---------Kind: 
                                                                                                           customResourceDeff
                              ________|_________                   /apis/apiextenstion.k8s.io/v1/customeresourcedefinitions
                             |                 |
/apis/apiregistrations.      |Kubernetese API  |
 k8s.io/v1/apiservices       |                 |
                             |_________________|
                                |           |
        aggregates APIS ---------------------------------------------Custom resources
           |                                                             | 
 
   warde.example.-->               API groups                     inlets.inlets.dev/v1alpha1
    com.v1alpha1 

       |                                                                       |
    flunders                        (Resources)                               tunnels
       |
     qux                            (Namespace)                                bar

       |                                                                        |
Kind:----------------------------< ---API OBject --->------------------------  Kind:------------->API OBject
    flunder                                                                      Tunnel
name:                                                                            name:
    fluinder -1                                                                    EC2-tun-1
(apis/wardle.example.come/v1aplha1/namespaces/foo/flunder)                    (apis/inlets.inlets.dev/v1alpha1/tunnels)


--https://github.com/praveen1994dec/Custom_Resource_Definition.git


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


Project4:
----------
EKS Cloud project see the documentation






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

4.list1 = ["jeans", "shirt"     ] == list data type and mutabale

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

To execute:
-python3 import os.py
-



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



                                     Monitoring
=================================================================================================================

Monitoring-
------------------

1 Walmart
------------
- Prometheus
- graphana
- xmaters
- Phone/Email
- SRE Engeeer - 8 AM - 8PM Level1/2
-               8:30pM- 8 AM/ Level1/2

2. Verizon
----------------
- Sentry
- ELK
- Aws cloud watch
- New relic

3. Infosys
-----------
- splunl
- datagod
- nagoss
- dynatries
- App dynamics
- 

Automation
-----------------------------------------
                                Xmatters       
                                   |
(can pull data from              Graphana -(Grpahana query languae),(Dashboard)
promethuse,mysql,infix,posgress)   |
inbuilt Time series databse-----Promethesu-(Scrapping the data from K8  in time interval ),( Prometheys Query language)
   or                              |             
  influx                           | (By deploying agents i interegrate prometheus and K8)
                                   |
                                   k8


1.Prometheus Query language to extract the kubernetes CPU and memory of a POD
-------------------------------------------------------------------------------
To extract the CPU and memory usage of a Kubernetes pod using Prometheus Query Language (PromQL), you can use the following queries. These queries assume you're using the kube-state-metrics and node-exporter or metrics-server to collect Kubernetes metrics.

CPU Usage for a Pod
To get the CPU usage of a specific pod in your cluster, you can query the container_cpu_usage_seconds_total metric:

promql
Copy
rate(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}[1m])
Explanation:

container_cpu_usage_seconds_total: Metric for the total CPU time consumed by containers.
pod="your-pod-name": Filter by the pod name.
namespace="your-namespace": Filter by the namespace.
[1m]: The rate() function computes the per-second average rate of increase over the last 1 minute.
Memory Usage for a Pod
To get the memory usage of a specific pod in your cluster, you can query the container_memory_usage_bytes metric:

promql
Copy
container_memory_usage_bytes{pod="your-pod-name", namespace="your-namespace"}
Explanation:

container_memory_usage_bytes: Metric for the memory usage (in bytes) of containers.
pod="your-pod-name": Filter by the pod name.
namespace="your-namespace": Filter by the namespace.
CPU and Memory Usage for All Pods in a Namespace
If you want to get the aggregate CPU and memory usage for all pods in a specific namespace, you can use the following queries:

CPU Usage (All Pods)
promql
Copy
sum(rate(container_cpu_usage_seconds_total{namespace="your-namespace"}[1m])) by (pod)
Memory Usage (All Pods)
promql
Copy
sum(container_memory_usage_bytes{namespace="your-namespace"}) by (pod)
Notes:
If you are looking for a specific container inside a pod, you can further refine your queries by adding the container label.
The rate() function helps calculate the per-second average over a given time range (e.g., [1m]).
Let me know if you need further clarification or adjustments based on your setup!

2.Grapahana query language for getting CPU of pod from prometheus
-------------------------------------------------------------------

In Grafana, when you're working with Prometheus as the data source, you'll be querying with PromQL (Prometheus Query Language) to pull metrics.

To retrieve CPU usage for a specific Kubernetes pod from Prometheus, you typically rely on the container_cpu_usage_seconds_total metric, which measures the total CPU time consumed by containers. You would filter this metric by the pod name and possibly the namespace to narrow the results.

Here are a few common queries to get CPU usage for pods:

1. CPU Usage for a Specific Pod:
If you want to get the CPU usage (in seconds) for a specific pod over time, you can use:

promql
Copy
rate(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}[1m])
Explanation:
container_cpu_usage_seconds_total: Total cumulative CPU time consumed by the container.
rate(...): Calculates the per-second rate of change for a counter metric (here, CPU usage).
{pod="your-pod-name", namespace="your-namespace"}: Filters the data for a specific pod and namespace.
[1m]: This indicates you're calculating the rate over the last 1 minute.
This query will give you the CPU usage in CPU cores per second.

2. CPU Usage for All Pods in a Namespace:
If you're interested in CPU usage for all pods within a specific namespace:

promql
Copy
sum(rate(container_cpu_usage_seconds_total{namespace="your-namespace"}[1m])) by (pod)
Explanation:
sum(...) by (pod): Sums the CPU usage for each pod in the given namespace and groups the results by the pod name.
This will return the CPU usage for each pod in the specified namespace.
3. CPU Usage (Total) Across All Pods:
To get the total CPU usage across all pods in the cluster:

promql
Copy
sum(rate(container_cpu_usage_seconds_total[1m]))
This will return the total CPU usage across all pods.

4. CPU Usage for a Pod, Relative to the Number of CPU Cores:
If you want to express CPU usage in a normalized way (e.g., as a percentage of available CPU cores):

promql
Copy
rate(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}[1m]) / count(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}) * 100
This query gives the CPU usage percentage by dividing the per-second CPU rate by the number of CPU cores allocated to the pod.

5. CPU Usage (Over Time) for a Specific Pod:
If you want to visualize CPU usage over time for a pod:

promql
Copy
avg(rate(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}[5m])) by (pod)
This query calculates the average CPU usage over a 5-minute window and groups it by pod. It's useful for showing a smoothed view of CPU usage over time.

6. CPU Usage for Containers in a Pod (Group by Container):
If you're monitoring multiple containers within a pod, you can get CPU usage per container:

promql
Copy
sum(rate(container_cpu_usage_seconds_total{pod="your-pod-name", namespace="your-namespace"}[1m])) by (container, pod)
This groups the CPU usage by container and pod, showing CPU usage for each container inside the pod.

Notes:
The rate() function is crucial in Prometheus as it helps to calculate the per-second rate of change for a counter metric. Without it, you might just get the cumulative counter value over time, which is less useful for monitoring trends.
Always adjust the 1m (1-minute) or [5m] window depending on how granular you want your data.
You can always check the list of available labels using Prometheus' query interface to see what other labels are available (like container, namespace, node, etc.).




3.graphana query for a mysql databse
------------------------------------------
 To create a query in Grafana for a MySQL database, you need to:

Set up the MySQL data source in Grafana.
Write SQL queries that pull the necessary data.
Here's an example of how to write a query for MySQL in Grafana.

Steps to Set Up:
Add MySQL as a Data Source:

Go to Grafana's web interface.
Click on the "Configuration" (gear icon) in the left menu.
Click on "Data Sources" and then "Add data source".
Select MySQL from the list and configure the connection (hostname, database name, credentials, etc.).
Create a Dashboard/Panel:

After configuring the data source, go to your Dashboard or create a new one.
Add a new Panel and select MySQL as the data source.
Sample Queries:
Here are a few example queries depending on the type of data you're working with:

1. Basic Query to Retrieve Data:
If you just want to select some basic data from a table, say you have a sales table, you might use:

sql
Copy
SELECT
  $__timeGroup(created_at, '5m') as time,
  SUM(amount) as total_sales
FROM sales
WHERE $__timeFilter(created_at)
GROUP BY time
ORDER BY time
Explanation:
__timeGroup is a Grafana function to group data based on time.
__timeFilter is a Grafana function to automatically filter by the time range selected in Grafana's UI.
SUM(amount) calculates the total sales per time period (in this case, 5 minutes).
2. Query for CPU or Resource Usage (if monitoring system metrics):
If you're tracking system metrics from a table like metrics:

sql
Copy
SELECT
  $__timeGroup(timestamp, '1h') as time,
  avg(cpu_usage) as average_cpu
FROM metrics
WHERE $__timeFilter(timestamp)
GROUP BY time
ORDER BY time
This gives you the average CPU usage over the past hour.

3. Query for Last N Records:
If you want to show the most recent records from a table:

sql
Copy
SELECT
  timestamp,
  metric_name,
  value
FROM metrics
ORDER BY timestamp DESC
LIMIT 10
4. Count Query for Event Frequency:
If you're counting events, for example:

sql
Copy
SELECT
  $__timeGroup(timestamp, '1h') as time,
  COUNT(*) as event_count
FROM events
WHERE $__timeFilter(timestamp)
GROUP BY time
ORDER BY time
Important Grafana Functions:
__timeGroup(): This function groups data by time intervals. Common intervals include '1m', '5m', '1h', etc.
__timeFilter(): Automatically applies the time range filter you’ve selected in the Grafana UI.
__interval: This is often used for aggregating data over a set time interval automatically.
Once you've written the query, Grafana will automatically visualize the results as time series data. You can then customize the panel type (Graph, Table, Gauge, etc.), and apply further transformations or alerts based on the data.

Let me know if you need further details or adjustments on your queries!




3.Prometheus configurations with targets as kubernetes
-------------------------------------------------------------

Setting up Prometheus to monitor Kubernetes involves configuring Prometheus to scrape metrics from the various Kubernetes components and services running in your cluster. Kubernetes exposes metrics in a format Prometheus can scrape, and you can configure Prometheus to discover these targets dynamically. Here's a step-by-step guide on how to configure Prometheus with Kubernetes targets.

1. Install Prometheus in Kubernetes
You can deploy Prometheus in Kubernetes using Helm or manually via manifests. Here’s how to do it with Helm, which is a quick and efficient way to manage Kubernetes applications.

Using Helm (Recommended):
Add the Prometheus Helm chart repository:

bash
Copy
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
Install Prometheus:

bash
Copy
helm install prometheus prometheus-community/kube-prometheus-stack
The kube-prometheus-stack chart includes Prometheus, Alertmanager, Grafana, and the necessary configurations for Kubernetes monitoring.

After installation, you can check the Prometheus pods:

bash
Copy
kubectl get pods -n default
By default, it will create a Prometheus deployment along with necessary RBACs, ConfigMaps, and service accounts.

2. Configure Prometheus to Discover Kubernetes Targets
Kubernetes uses service discovery to allow Prometheus to automatically find and scrape the necessary targets. This can be configured through the Prometheus configuration file (prometheus.yml), but with Helm, most of this configuration is set automatically.

However, you can still modify or check the configuration in the Prometheus Helm chart values.

Configuring Kubernetes Service Discovery:
Prometheus supports a variety of service discovery mechanisms. For Kubernetes, it's usually done by using the kubernetes_sd_configs option. Here's an example of how you would define it in prometheus.yml:

yaml
Copy
scrape_configs:
  - job_name: 'kubernetes-pods'
    kubernetes_sd_configs:
      - role: pod
    relabel_configs:
      - source_labels: [__meta_kubernetes_pod_label_app]
        target_label: app
3. Service Discovery with Kubelet, Nodes, and Pods
In Kubernetes, you can configure Prometheus to scrape the following types of targets:

Kubelet metrics (on each node)
Pod metrics (from specific services/pods)
Node metrics (via the node-exporter)
Here's how you can configure Prometheus to scrape these targets:

Example: Scraping Metrics from Kubelets
yaml
Copy
scrape_configs:
  - job_name: 'kubernetes-nodes'
    kubernetes_sd_configs:
      - role: node
    relabel_configs:
      - source_labels: [__meta_kubernetes_node_label_kubernetes_io_hostname]
        target_label: kubernetes_node
Example: Scraping Metrics from Pods
yaml
Copy
scrape_configs:
  - job_name: 'kubernetes-pods'
    kubernetes_sd_configs:
      - role: pod
    relabel_configs:
      - source_labels: [__meta_kubernetes_pod_name]
        target_label: pod_name
4. Configure RBAC for Prometheus
Prometheus needs to have the correct permissions to query the Kubernetes API and scrape the necessary metrics. This can be done by configuring Role-Based Access Control (RBAC) permissions for Prometheus. If you're using the kube-prometheus-stack Helm chart, the necessary RBAC permissions are usually created automatically. However, if you're doing it manually, here's an example of what you need to include:

Example RBAC Permissions:
yaml
Copy
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: monitoring
  name: prometheus
rules:
  - apiGroups: [""]
    resources: ["pods", "services", "endpoints"]
    verbs: ["get", "list"]
  - apiGroups: ["extensions"]
    resources: ["ingresses"]
    verbs: ["get", "list"]
  - apiGroups: ["metrics.k8s.io"]
    resources: ["nodes", "pods"]
    verbs: ["get", "list"]
5. Expose Prometheus Web UI
By default, Prometheus is exposed internally within the Kubernetes cluster, but you may want to access it externally for monitoring and troubleshooting. You can expose Prometheus through a Kubernetes service of type LoadBalancer or NodePort.

For example, with Helm, you can expose it by adding the following to your values.yaml file:

yaml
Copy
prometheus:
  service:
    type: LoadBalancer
    port: 9090
Then, upgrade your Helm release:

bash
Copy
helm upgrade prometheus prometheus-community/kube-prometheus-stack -f values.yaml
Alternatively, you can manually edit the Prometheus service in the Kubernetes cluster to expose it.

6. Configure Alerts (Optional)
Prometheus also supports alerting, which you can configure to notify you when certain thresholds are met. You would typically set up Alertmanager for this.

Example alertmanager.yml (configured via Helm or a ConfigMap):

yaml
Copy
global:
  resolve_timeout: 5m

route:
  group_by: ['alertname']
  group_wait: 10s
  group_interval: 5m
  repeat_interval: 3h
  receiver: 'email-alert'

receivers:
  - name: 'email-alert'
    email_configs:
      - to: 'your-email@example.com'
        send_resolved: true
7. Grafana Integration
The kube-prometheus-stack chart comes with Grafana preconfigured. You can access Grafana to visualize the Prometheus metrics by setting it up with the appropriate values:

yaml
Copy
grafana:
  adminPassword: 'yourpassword'
  service:
    type: LoadBalancer
Once Grafana is running, you can access the dashboards using the default Prometheus dashboards or create your own to visualize Kubernetes metrics.

Conclusion
With Helm and Prometheus's built-in Kubernetes service discovery, you can quickly start monitoring Kubernetes clusters. Prometheus will automatically discover and scrape metrics from Kubernetes components, including nodes, pods, and the Kubernetes API server. You can then visualize this data using Grafana or set up alerts to be notified when critical thresholds are crossed.



Java- Maven/ Maven repo
Nodejs- npm/node
Andriod- Graddle
K8- helm/helm repo
docker- dockerfile/dockerhub



K8-----> helm package---> to share and deploy in other k8 pods



Standard Helm Chart Directory Structure with example of each and every files
--------------------------------------------------

 Here's the standard Helm Chart directory structure with examples of each file and directory:

Helm Chart Directory Structure Example
pgsql
Copy
my-chart/
├── .helmignore
├── Chart.yaml
├── values.yaml
├── charts/
│   └── redis-helm-chart-1.0.0.tgz  (example of a dependency chart)
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   └── configmap.yaml
├── README.md
└── values.schema.json (optional)
1. .helmignore
This file works like .gitignore and tells Helm which files should be excluded when packaging or deploying the chart. It's useful for excluding local development files, temporary files, and unnecessary artifacts.

Example:

plaintext
Copy
# Ignore temporary files
*.log
*.tmp

# Ignore specific directories
.idea/
.vscode/

# Ignore markdown files (except README.md)
*.md
2. Chart.yaml
This file contains the metadata about the Helm chart, like its name, version, description, and any dependencies.

Example:

yaml
Copy
apiVersion: v2
name: my-app
description: A Helm chart for deploying MyApp
version: 1.0.0
appVersion: "2.0"
dependencies:
  - name: redis
    version: "6.0.0"
    repository: "https://charts.bitnami.com/bitnami"
3. values.yaml
This file contains the default configuration values for your chart. Users can override these values when they deploy the chart.

Example:

yaml
Copy
replicaCount: 2
image:
  repository: myapp
  tag: "1.0.0"
  pullPolicy: IfNotPresent
service:
  type: ClusterIP
  port: 80
resources: {}
ingress:
  enabled: true
  annotations: {}
  path: /
  hosts:
    - host: myapp.local
      paths: []
4. charts/
This directory contains subcharts, which are other charts that your chart depends on. Helm will automatically look for dependencies here and install them when running helm install. You can also use helm dependency update to fetch remote charts.

Example (subchart of Redis):

Copy
charts/
└── redis-helm-chart-1.0.0.tgz
5. templates/
This folder contains all the Kubernetes resource templates. These files are usually YAML files with Helm template syntax embedded (e.g., {{ .Values.someField }}) to dynamically generate Kubernetes resources.

deployment.yaml
Defines the Deployment resource for your application.

Example:

yaml
Copy
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}-myapp
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app: {{ .Release.Name }}-myapp
  template:
    metadata:
      labels:
        app: {{ .Release.Name }}-myapp
    spec:
      containers:
        - name: myapp
          image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
          ports:
            - containerPort: 80
          resources:
            {{- toYaml .Values.resources | nindent 12 }}
service.yaml
Defines the Service resource for your application.

Example:

yaml
Copy
apiVersion: v1
kind: Service
metadata:
  name: {{ .Release.Name }}-myapp-service
spec:
  selector:
    app: {{ .Release.Name }}-myapp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: {{ .Values.service.type }}
ingress.yaml
Defines the Ingress resource for routing traffic to your app.

Example:

yaml
Copy
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: {{ .Release.Name }}-myapp-ingress
  annotations:
    {{- toYaml .Values.ingress.annotations | nindent 4 }}
spec:
  rules:
    - host: {{ .Values.ingress.hosts[0].host }}
      http:
        paths:
          - path: {{ .Values.ingress.path }}
            pathType: Prefix
            backend:
              service:
                name: {{ .Release.Name }}-myapp-service
                port:
                  number: 80
configmap.yaml
Defines a ConfigMap resource for storing configuration data.

Example:

yaml
Copy
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-myapp-config
data:
  app-config: |
    setting1: {{ .Values.someSetting }}
    setting2: {{ .Values.anotherSetting }}
6. README.md
This file is for chart documentation. It explains how to use the chart, provides examples, and includes any relevant configuration options.

Example:

markdown
Copy
# MyApp Helm Chart

This Helm chart deploys MyApp to your Kubernetes cluster.

## Installation

To install the chart with the release name `myapp`:

```bash
helm install myapp ./my-chart
Configuration
Parameter	Description	Default Value
replicaCount	Number of replicas	1
image.repository	Image repository	myapp
image.tag	Image tag	1.0.0
service.type	Service type	ClusterIP
Ingress
To enable ingress, modify values.yaml:

yaml
Copy
ingress:
  enabled: true
  hosts:
    - host: myapp.local
      paths: []
pgsql
Copy

---

### 7. **`values.schema.json` (optional)**

This is an optional file for providing a schema definition for your `values.yaml` file. It allows for validation of user input and documentation of configuration fields.

**Example:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "replicaCount": {
      "type": "integer",
      "default": 1
    },
    "image": {
      "type": "object",
      "properties": {
        "repository": {
          "type": "string"
        },
        "tag": {
          "type": "string"
        }
      }
    },
    "service": {
      "type": "object",
      "properties": {
        "type": {
          "type": "string",
          "enum": ["ClusterIP", "NodePort", "LoadBalancer"]
        }
      }
    }
  }
}
Conclusion:
The standard Helm chart directory structure is designed to be simple and organized. The most common files are:

Chart.yaml – Chart metadata.
values.yaml – Default values for configuration.
templates/ – Kubernetes resource templates.
README.md – Documentation.
Each file plays a crucial role in making your Helm chart reusable, maintainable, and easy to deploy in Kubernetes environments.

Would you like to dive deeper into any specific file or concept?





4jenkins installation on kubernetes with helm charts
------------------------------------------------------

To install Jenkins on Kubernetes using Helm, you can follow these steps:

1. Install Helm (if you haven't already)
If you don't have Helm installed, you'll need to do that first. You can install Helm using the following commands based on your system:

macOS (with Homebrew):
bash
Copy
brew install helm
Linux:
bash
Copy
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
Windows (via Chocolatey):
bash
Copy
choco install kubernetes-helm
2. Add Jenkins Helm Chart Repository
Jenkins provides an official Helm chart that you can use for installation. Add the official Jenkins Helm chart repository:

bash
Copy
helm repo add jenkins https://charts.jenkins.io
helm repo update
3. Install Jenkins Using Helm
You can now install Jenkins on your Kubernetes cluster using Helm. To install Jenkins, run:

bash
Copy
helm install jenkins jenkins/jenkins --namespace jenkins --create-namespace
This command will:

Install Jenkins in the jenkins namespace (it will create the namespace if it doesn’t exist).
The release will be named jenkins.
4. Check Installation
To ensure Jenkins was installed successfully, you can check the status of the deployment:

bash
Copy
kubectl get pods -n jenkins
You should see Jenkins pods running. It may take a minute or so for Jenkins to be fully initialized.

5. Access Jenkins
By default, the Jenkins installation via Helm will expose the Jenkins UI using a LoadBalancer service (depending on your Kubernetes environment). To check the external IP address, you can run:

bash
Copy
kubectl get svc -n jenkins
Look for the EXTERNAL-IP of the jenkins service.

If you're using Minikube (local Kubernetes):
If you're using Minikube, you can access the Jenkins UI through the Minikube tunnel:

bash
Copy
minikube tunnel
Then access Jenkins via http://localhost:8080 or the URL provided.

6. Retrieve the Jenkins Admin Password
Once the Jenkins pods are running, you can retrieve the initial admin password to log in to the Jenkins UI:

bash
Copy
kubectl get secret --namespace jenkins jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode
This will give you the password that you can use to log in as the Jenkins admin user.

7. Post-Installation Configurations
After logging into Jenkins, you may need to install additional plugins or configure Jenkins to suit your needs.

Customizing Your Jenkins Installation
You can customize the Helm chart values by creating a custom values.yaml file. For example:

yaml
Copy
controller:
  installPlugins:
    - kubernetes:1.30.0
    - workflow-aggregator:2.6
    - git:4.10.0
  jenkinsUriRoot: "/jenkins"
Then, install Jenkins using the custom values file:

bash
Copy
helm install jenkins jenkins/jenkins --namespace jenkins --create-namespace -f values.yaml
8. Upgrade Jenkins (if needed)
If you want to upgrade Jenkins in the future, you can use:

bash
Copy
helm upgrade jenkins jenkins/jenkins --namespace jenkins
9. Uninstall Jenkins
If you ever need to uninstall Jenkins, you can do so with:

bash
Copy
helm uninstall jenkins --namespace jenkins
This will remove the release, and if you want to delete the namespace as well:

bash
Copy
kubectl delete namespace jenkins



Project  5
--------------




                                        Shell Scripting
================================================================================================================================

1  Commands in shell scripting
-----------------------------------------
 a=b } variables and datatpes
 b=c

-linux system
-API automations
-backups recovery

Linux systems
---------------
types of logins
-sh
-ksh
-nologin
-bash

Command
- SED - stream editor - file operations,variable operations
- AWK 
- YUM
- APT
- FUNCTIONS
- automation
- scenarios
- software
- grep
- find
- mtime
- top
- ctime
- df

1. sed command - sed s/maganger/heydeveops/g text.txt
               - sed -n '1,3'p test.sh ----> print 1 to 3 lines [p -> print /n-> number]

2. awk '{print}' test.sh  --- print the whole file

3. awk /manager/'{print}' test.sh prints lines with "manager" word
4. awk -F'[.]''/^version/{print $1"."$2"."$4+1}' test.sh
version=1.2.3.4 -- Version increment

5. sed 's/tenth/eleaven//=g' test.sh -> Replace a value in a file
   hello=Devops=learners

6.echo $hello |sed's/=/ /g' | awk '{print $2}'


automation -1Script project of sending file to jfrog repo:
--------------------------------------------------

 automation-2
-----------------


https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-labels/#api-group-labels





shell script to find the log file with older that last 7 days
----------------------------------------------------------------

#!/bin/bash

# Directory where log files are located (you can modify this path)
LOG_DIR="/path/to/log/directory"

# Find files older than 7 days and print their names
find "$LOG_DIR" -type f -name "*.log" -mtime +7
Explanation:
find: Command to search for files.
"$LOG_DIR": The directory where the log files are stored (you can change this to the directory where your log files are).
-type f: Restricts the search to files (ignoring directories).
-name "*.log": Searches only for files with the .log extension. Adjust this if your logs have a different extension.
-mtime +7: Finds files modified more than 7 days ago (+7 means "greater than 7 days").
How to use it:
Save the script in a file, e.g., find_old_logs.sh.
Make the script executable:
bash
Copy
chmod +x find_old_logs.sh
Run the script:
bash
Copy
./find_old_logs.sh


Functions with shell:
-------------------------
#!/bin/bash

# Function to find log files older than 7 days
find_old_logs() {
    # Set the directory to search and the log file extension
    local directory="$1"
    local extension="$2"
    
    # Check if the directory exists
    if [ ! -d "$directory" ]; then
        echo "Directory $directory does not exist."
        exit 1
    fi

    # Find files older than 7 days
    find "$directory" -type f -name "*.$extension" -mtime +7
}

# Function to send an email with the log results
send_email() {
    local email_subject="$1"
    local email_recipient="$2"
    local email_body="$3"

    echo -e "$email_body" | mail -s "$email_subject" "$email_recipient"
}

# Main script logic

# Set your directory and email details
log_directory="/path/to/logs"           # Modify this with your log directory
log_extension="log"                     # Modify this if your logs have a different extension
email_recipient="recipient@example.com" # Modify with your recipient email
email_subject="Logs Older Than 7 Days"  # Subject for the email

# Find the logs older than 7 days
log_files=$(find_old_logs "$log_directory" "$log_extension")

# Check if we found any old logs
if [ -z "$log_files" ]; then
    email_body="No log files older than 7 days were found."
else
    email_body="The following log files are older than 7 days:\n\n$log_files"
fi

# Send email
send_email "$email_subject" "$email_recipient" "$email_body"

echo "Email sent to $email_recipient with the results."


For loop with array in the shelll script:
------------------------------------------------
## declare an array variable
declare -a arr=("element1" "element2" "element3")

## now loop through the above array
for i in "${arr[@]}"
do
   echo "$i"
   # or do whatever with individual element of the array
done

# You can access them using echo "${arr[0]}", "${arr[1]}" also
Also works for multi-line array declaration

declare -a arr=("element1" 
                "element2" "element3"
                "element4"
                )

Write a shell script to read the data from below log file and get the ip address  
---------------------------------------------------------------------------------------
https://www.onlinegdb.com/online_bash_shell



03/22 08:51:06 TRACE  :...read_physical_netif: Home list entries returned = 7
03/22 08:51:06 INFO   :...read_physical_netif: index #0, interface VLINK1 has address 129.1.1.1, ifidx 0
03/22 08:51:06 INFO   :...read_physical_netif: index #1, interface TR1 has address 9.37.65.139, ifidx 1
03/22 08:51:06 INFO   :...read_physical_netif: index #2, interface LINK11 has address 9.67.100.1, ifidx 2
03/22 08:51:06 INFO   :...read_physical_netif: index #3, interface LINK12 has address 9.67.101.1, ifidx 3
03/22 08:51:06 INFO   :...read_physical_netif: index #4, interface CTCD0 has address 9.67.116.98, ifidx 4
03/22 08:51:06 INFO   :...read_physical_netif: index #5, interface CTCD2 has address 9.67.117.98, ifidx 5
03/22 08:51:06 INFO   :...read_physical_netif: index #6, interface LOOPBACK has address 127.0.0.1, ifidx 0
03/22 08:51:06 INFO   :....mailslot_create: creating mailslot for timer
03/22 08:51:06 INFO   :...mailbox_register: mailbox allocated for timer


Desired Output

129.1.1.1
9.37.65.139
9.67.100.1
9.67.116.98


You can use a simple shell script to extract the IP addresses from the log file. Here’s a script that will read the log file, search for lines containing IP addresses, and then print only those IPs:

bash
Copy
#!/bin/bash

# Define the log file path
log_file="logfile.txt"  # Update this with the actual path to your log file

# Extract IP addresses using grep and awk
grep -oP '\d+\.\d+\.\d+\.\d+' "$log_file" | grep -v '127.0.0.1'
Explanation:
grep -oP '\d+\.\d+\.\d+\.\d+':
-o: Tells grep to only output the matched part (in this case, the IP address).
-P: Enables Perl-style regex for more advanced pattern matching.
\d+\.\d+\.\d+\.\d+: This regular expression matches an IP address pattern (e.g., 9.37.65.139).
grep -v '127.0.0.1': This filters out the 127.0.0.1 address, as it’s the loopback address, which you may not want to include.
How to run the script:
Save the script to a file, e.g., extract_ips.sh.
Make it executable by running:
bash
Copy
chmod +x extract_ips.sh
Run the script:
bash
Copy
./extract_ips.sh
Sample Output:
Copy
129.1.1.1
9.37.65.139
9.67.100.1
9.67.116.98


===================================================================================================
                                        Teraform

- T/f automation to spin up the infra in count value
- spin up my infra in multicloud in AWS AZURE GCP
- versioning of infra is done with T/F
- state of infra is managed
- commands
- life cycle policies to delete or make changes in resources
- modules 





values--->--tfvars---->--variables----->--tf individual files


resource "aws_instance" "example_server" {
  ami           = "ami-04e914639d0cca79a"
  instance_type = "t2.micro"
  count         = 10

  tags = {
    Name = "JacksBlogExample"
  }
}


create terraform code to spin up 10 ec2 instances with different. ami
--------------------------------------------------------------------------
To spin up 10 EC2 instances with different AMIs using Terraform, you would need to define the EC2 instances in a Terraform configuration, specifying the AMIs for each one. Here's an example of how to achieve this:

Terraform Code Example:
hcl
Copy
provider "aws" {
  region = "us-west-2"  # Set the AWS region
}

resource "aws_instance" "ec2_instance" {
  count             = 10  # Creates 10 instances
  ami               = var.ami_ids[count.index]  # Assign a unique AMI ID for each instance
  instance_type     = "t2.micro"  # Instance type
  key_name          = "my-key-pair"  # Replace with your key pair name
  associate_public_ip_address = true  # Assign public IP

  tags = {
    Name = "EC2 Instance ${count.index + 1}"
  }

  # You can specify other parameters such as security groups, user data, etc.
}

variable "ami_ids" {
  description = "List of AMI IDs for each EC2 instance"
  type        = list(string)
  default = [
    "ami-xxxxxxxxxxxxxxxxx",  # Replace with your AMI IDs
    "ami-yyyyyyyyyyyyyyyyy",
    "ami-zzzzzzzzzzzzzzzz",
    "ami-aaaaaaaaaaaaaaaaa",
    "ami-bbbbbbbbbbbbbbbb",
    "ami-cccccccccccccccc",
    "ami-dddddddddddddddd",
    "ami-eeeeeeeeeeeeeeee",
    "ami-fffffffffffffffff",
    "ami-gggggggggggggggg"
  ]
}
Explanation:
provider "aws": Specifies the AWS region where the EC2 instances will be created.
resource "aws_instance" "ec2_instance": Defines the EC2 instance resource. The count meta-argument is used to create 10 instances.
ami: The AMI ID is dynamically chosen using count.index to select a different AMI for each instance from the ami_ids list.
instance_type: Specifies the instance type, here it's set to t2.micro. You can change this as needed.
key_name: Specifies the key pair name to access the instances. Replace with your actual key pair.
variable "ami_ids": A variable containing a list of 10 AMI IDs. Each instance will use a different AMI from this list.
Usage:
Replace the ami_ids list with actual AMI IDs that you want to use for the instances.
Replace the region, key_name, and other parameters as necessary.
Initialize and apply the Terraform configuration:
bash
Copy
terraform init
terraform apply

create terraform code to spin up 10 ec2 instances with different. ami using for each loop
-----------------------------------------------------------------------------------------
To create 10 EC2 instances with different AMIs using a for_each loop in Terraform, you can define a map of AMI IDs and then use the for_each construct to iterate over that map.

Here is an example of how to do this:

Terraform Code Example:
hcl
Copy
provider "aws" {
  region = "us-west-2"  # Set the AWS region
}

resource "aws_instance" "ec2_instance" {
  for_each           = var.ami_map  # Loop over the ami_map variable
  ami                = each.value  # Each value in the map is an AMI ID
  instance_type      = "t2.micro"  # Instance type
  key_name           = "my-key-pair"  # Replace with your key pair name
  associate_public_ip_address = true  # Assign public IP

  tags = {
    Name = "EC2 Instance ${each.key}"  # Name the instances as EC2 Instance 1, 2, etc.
  }

  # You can specify other parameters such as security groups, user data, etc.
}

variable "ami_map" {
  description = "Map of AMI IDs for each EC2 instance"
  type        = map(string)
  default = {
    "instance_1" = "ami-xxxxxxxxxxxxxxxxx",  # Replace with your AMI IDs
    "instance_2" = "ami-yyyyyyyyyyyyyyyyy",
    "instance_3" = "ami-zzzzzzzzzzzzzzzz",
    "instance_4" = "ami-aaaaaaaaaaaaaaaaa",
    "instance_5" = "ami-bbbbbbbbbbbbbbbb",
    "instance_6" = "ami-cccccccccccccccc",
    "instance_7" = "ami-dddddddddddddddd",
    "instance_8" = "ami-eeeeeeeeeeeeeeee",
    "instance_9" = "ami-fffffffffffffffff",
    "instance_10" = "ami-gggggggggggggggg"
  }
}
Explanation:
provider "aws": Specifies the AWS region where the EC2 instances will be created.
resource "aws_instance" "ec2_instance": The for_each loop is used to create multiple instances based on the keys in the ami_map variable.
for_each = var.ami_map: This allows you to loop over the ami_map and create one instance per key-value pair.
ami = each.value: each.value refers to the AMI ID for the instance, as it loops through the map.
Name = "EC2 Instance ${each.key}": Names the instances as EC2 Instance 1, EC2 Instance 2, etc., using the key from the map.
variable "ami_map": A map variable that holds the AMI IDs for each instance. Each key represents a unique instance (instance_1, instance_2, etc.), and the corresponding value is the AMI ID.
Usage:
Replace the ami_map values with actual AMI IDs.
Replace the region, key_name, and other parameters as necessary.
Initialize and apply the Terraform configuration:
bash
Copy
terraform init
terraform apply



==============================================================

AWS
- VPC- Virutal Private cloud
- Internet Gateway
- Availabitlity Zones
- subnets
- NACL'S-Network access control list- it can allow or deny the IP's
- SG - security group
- EC2
- ASG- auto scaling group
- LB - load balancer 
- ACM- AMAZON CERITFICATE MANAGER 
- CFT/CDN- CLOUD FRONT OR CONT DELIVERY NETWORK
- LAMBDA
- RDS
- S3
- SNS- SIMPPLE NOITIFICATION SERVICE
- SQS- SIMPLE QUEUE SERVICE
- VPC ENDPOINT
- EMR- ELASTIC MAP REDUCE 
- EKS - ELASTIC KUBERNET SERVICE
- IAM - 
- VPN GATEWAYS
- CLOUD WATCH MONITORING

AWS Cloud Network Architecture
---------------------------------

                     Internet gateway
                          | 
                      ROUTE TABLES
                          |
                   target    destination

                          |
                          VPC                    CIDR, SUBNET      
                          |

         NACL- Network access control list- it can allow or deny the IP's

                          |
                       SUBNET'S
                       ---------
                       Public SUBNET 

AZ1           NAT GATEWAY- Network address translatro

                      Private  SUBNET

                       SUBNET'S
                       ---------
                       Public SUBNET
AZ2              NAT GATEWAY- Network address translatro
 
                     Private  SUBNET


                  

local->subnetdestination->VPC,NAT gateway-> Virtual PrivateE atgateway, vpc endpoint



Cloud Frontier architecture
------------------------------

                           cloudfront (Cache method to improve the latency issues in the networking)
                              |
                              |
                              r53-----> LB----->  EC2,EKS,LAMBDA -----> db


 
R53(DNS) -Domain name system                         _____
- Round robin(routing mechanism)        |-->-------- |____|
                                        |
               R53--->_-----------------| 
                                        |---->------   ____
                                                      |____|
- weighted- percentage based routing, say if i want to route 60 percent to 1 server and the rest t40 to 2 server


                                                     _____
                                        |-->-60----- |____|
                                        |
               R53------->--------------| 
                                        |----40>------ ____
                                                      |____|

- geo location - Areawise,locationwise.- User willbe getting response nearer to his location/fster response
- latency based routing




 Loadbaolancer
   |
=-------------------------------------------------------------
  |                                                     |
Application LB                                        Network lob

- When i have                                   - One way traffic communication[ youtube]
   25 certificates with
  me will use APP LB (add your certificate
  to your load balancer
  make it a layer 7 network

- Context wpath 2 query base qouting            - ssl termination at POD not at LB
  eg www/walmart/groceries/meat

- SSL Termination( Secure scoket layer)         - certificates can be added
   it will check at loabalancer if it is valid
   if not valid it will terminate
- you can watch for erro's [500, 404            - when you need high traffice flow
- health checks
- 3 way TLS handshake happens in Application LB
   requst sent, processe and acknowledment back



S3  BUCKETS
-------------

- Backup of data
- retrival of data
- storage of data
- Name of the bucket should be small lettets
- unique bucket name
- bucket polices
- type of bucket and type of data, amount of data and amount of time is inversily proportional to cost of bucket

- type of buckets:
----------------------
   - standard bucket
   - infrequent access bucket
   - glacier - monthyl acess 
   - Intelligent tiering bucket-- based on access ratio it will save the data accordingly
   - one zone bucket ---------------One availabity zone
   - deep glacier/deep archieve
   - snowball
   

CloudWatch
--------------
Montoring your entire infra

-Graphana
-prometheus
-splunk


Database
-----------------
Tb of data
----------------
- My qql
- postgress
- cosmos db
  - no sql
  - clidck evenv based database
- dynamo db
  - jason based DB


big data platforms
------------------------
EMR - Elastic map reduce



                                                 ANSIBLE
 ===========================================================================================


Ansible
---------
- Infra
- Automation
- Bootstrapping of server
- Bulk deployments



                                                    
                                                     |----
  Parent-------> SSH Connection or RDP Windowds----->|---- 100 servers
  server                                             |----
(public key)----------------------------------------->/autothorizedkey/public key in 100 servers paths


Ansible  needs below to peform task
-------------------------------------
- host inventory file( consits of 100 servers ip address)
- playbook yaml
- SSH Connection


Playbook
-----------
host: it will point to the inventory file
name: name of playbook
become: sudo permission
user  username
tasks:
    -name: copy file from parent server and put it in achild server
     copy: module
     content: "heydevops"
     destination: "/etc/text"

https://docs.ansible.com/ansible/2.8/modules/list_of_all_modules.html

copy – Copy files to remote locations
------------------------------------------
- name: Copy file with owner and permissions
  copy:
    src: /srv/myfiles/foo.conf
    dest: /etc/foo.conf
    owner: foo
    group: foo
    mode: '0644'

lineinfile – Manage lines in text files
------------------------------------------
# NOTE: Before 2.3, option 'dest', 'destfile' or 'name' was used instead of 'path'
- name: Ensure SELinux is set to enforcing mode
  lineinfile:
    path: /etc/selinux/config
    regexp: '^SELINUX='
    line: SELINUX=enforcing


yum – Manages packages with the yum package manager
-----------------------------------------------------
- name: install the latest version of Apache
  yum:
    name: httpd
    state: latest



---

- name: 'Test playbook to write content into a file'
  hosts: localhost
  gather_facts: false
  vars:
    content: 'Test_Content_Line'
    filepath: '/etc/hello.txt'
  tasks:

    - name: "Write content into a file"
      copy:
        dest: "{{ filepath }}"
        content: "{{ content }}"

    - name: "Check file {{ filepath }} stat result"
      stat:
        path: "{{ filepath }}"
      register: st

    - name: "Check if file {{ filepath }} exists"
      fail:
        msg: "{{ filepath }} doesnt exist"
      when: not st.stat.exists | bool

    - name: "Get {{ filepath }} content"
      command: "cat {{ filepath }}"
      register: cnt

    - name: "Check if {{ filepath }} content is correct"
      fail:
        msg: "{{ filepath }} doesnt have the correct content"
      when: '"{{ content }}" not in cnt.stdout'



aws_s3 – manage objects in S3
--------------------------------
- name: Simple PUT operation
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    src: /usr/local/myfile.txt
    mode: put

- name: Simple PUT operation in Ceph RGW S3
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    src: /usr/local/myfile.txt
    mode: put
    rgw: true
    s3_url: "http://localhost:8000"

- name: Simple GET operation
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    dest: /usr/local/myfile.txt
    mode: get

- name: Get a specific version of an object.
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    version: 48c9ee5131af7a716edc22df9772aa6f
    dest: /usr/local/myfile.txt
    mode: get

- name: PUT/upload with metadata
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    src: /usr/local/myfile.txt
    mode: put
    metadata: 'Content-Encoding=gzip,Cache-Control=no-cache'

- name: PUT/upload with custom headers
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    src: /usr/local/myfile.txt
    mode: put
    headers: 'x-amz-grant-full-control=emailAddress=owner@example.com'

- name: List keys simple
  aws_s3:
    bucket: mybucket
    mode: list

- name: List keys all options
  aws_s3:
    bucket: mybucket
    mode: list
    prefix: /my/desired/
    marker: /my/desired/0023.txt
    max_keys: 472

- name: Create an empty bucket
  aws_s3:
    bucket: mybucket
    mode: create
    permission: public-read

- name: Create a bucket with key as directory, in the EU region
  aws_s3:
    bucket: mybucket
    object: /my/directory/path
    mode: create
    region: eu-west-1

- name: Delete a bucket and all contents
  aws_s3:
    bucket: mybucket
    mode: delete

- name: GET an object but don't download if the file checksums match. New in 2.0
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    dest: /usr/local/myfile.txt
    mode: get
    overwrite: different

- name: Delete an object from a bucket
  aws_s3:
    bucket: mybucket
    object: /my/desired/key.txt
    mode: delobj

ec2 – create, terminate, start or stop an instance in ec2
--------------------------------------------------------------


# Note: These examples do not set authentication details, see the AWS Guide for details.

# Basic provisioning example
- ec2:
    key_name: mykey
    instance_type: t2.micro
    image: ami-123456
    wait: yes
    group: webserver
    count: 3
    vpc_subnet_id: subnet-29e63245
    assign_public_ip: yes



vpc ansible module
----------------------
The VPC Ansible module is used to manage AWS Virtual Private Clouds (VPCs) within Ansible playbooks. Ansible provides the amazon.aws.ec2_vpc_net module to create, modify, and delete VPCs.

1. Install Dependencies
Ensure you have the required dependencies installed:

bash
Copy
Edit
pip install boto3 botocore ansible
ansible-galaxy collection install amazon.aws
2. Example Playbook
Here’s a basic playbook to create a VPC:

yaml
Copy
Edit
- name: Create AWS VPC
  hosts: localhost
  gather_facts: no
  tasks:
    - name: Create a new VPC
      amazon.aws.ec2_vpc_net:
        name: my-vpc
        cidr_block: 10.0.0.0/16
        region: us-east-1
        state: present
      register: vpc

    - name: Display VPC ID
      debug:
        msg: "VPC created with ID {{ vpc.vpc.id }}"
3. Parameters
name: The name of the VPC (tagged Name).
cidr_block: The IP range for the VPC.
region: AWS region where the VPC will be created.
state: present to create, absent to delete.
4. Deleting a VPC
To delete an existing VPC, set state: absent:

yaml
Copy
Edit
- name: Delete AWS VPC
  hosts: localhost
  gather_facts: no
  tasks:
    - name: Delete VPC
      amazon.aws.ec2_vpc_net:
        name: my-vpc
        region: us-east-1
        state: absent
5. Adding a Subnet
Use amazon.aws.ec2_vpc_subnet:

yaml
Copy
Edit
- name: Create subnet in VPC
  hosts: localhost
  gather_facts: no
  tasks:
    - name: Create subnet
      amazon.aws.ec2_vpc_subnet:
        vpc_id: "{{ vpc.vpc.id }}"
        cidr: 10.0.1.0/24
        region: us-east-1
        state: present
Would you like help integrating this into an automation workflow? 🚀

You said:



Ansible playbook automation to deploy the pods in kubernetes 
-------------------------------------------------------------------

ChatGPT said:
Here’s an Ansible playbook to automate the deployment of Kubernetes pods. It assumes that:

You have kubectl and kubeconfig set up on the control node.
Your Kubernetes cluster is accessible from the Ansible host.
You have the kubernetes.core collection installed.
1. Install Required Dependencies
Ensure Ansible has the necessary Kubernetes modules:

bash
Copy
Edit
pip install kubernetes
ansible-galaxy collection install kubernetes.core
2. Ansible Playbook for Deploying Pods
This playbook deploys a simple Nginx pod into a Kubernetes cluster.

yaml
Copy
Edit
- name: Deploy Kubernetes Pods
  hosts: localhost
  gather_facts: no
  tasks:

    - name: Create a Kubernetes Namespace
      kubernetes.core.k8s:
        name: demo-namespace
        api_version: v1
        kind: Namespace
        state: present

    - name: Deploy Nginx Pod
      kubernetes.core.k8s:
        state: present
        definition:
          apiVersion: v1
          kind: Pod
          metadata:
            name: nginx-pod
            namespace: demo-namespace
          spec:
            containers:
              - name: nginx
                image: nginx:latest
                ports:
                  - containerPort: 80

    - name: Verify Pod Status
      kubernetes.core.k8s_info:
        kind: Pod
        namespace: demo-namespace
        name: nginx-pod
      register: pod_info

    - name: Show Pod Details
      debug:
        msg: "Pod Status: {{ pod_info.resources[0].status.phase }}"
3. Running the Playbook
Save the playbook as deploy_pod.yml, then execute:

bash
Copy
Edit
ansible-playbook deploy_pod.yml
4. Verifying the Deployment
After execution, check the pod status manually:

bash
Copy
Edit
kubectl get pods -n demo-namespace
5. Cleanup (Delete the Pod & Namespace)
To remove the deployed pod and namespace:

yaml
Copy
Edit
- name: Cleanup Kubernetes Deployment
  hosts: localhost
  gather_facts: no
  tasks:

    - name: Delete Nginx Pod
      kubernetes.core.k8s:
        state: absent
        kind: Pod
        name: nginx-pod
        namespace: demo-namespace

    - name: Delete Namespace
      kubernetes.core.k8s:
        state: absent
        kind: Namespace
        name: demo-namespace
Would you like me to extend this to deploy a full-fledged application (Deployment, Service, Ingress, etc.)? 🚀

Messages beyond this point are only visible to you



Attach

Search

Reason

Voice
ChatGPT can make mistakes. Check important info.




Roles:
--------------
ansible roles folder structure

The Ansible roles folder structure is designed to help you organize your automation tasks in a modular, reusable, and scalable way. This structure is widely used in Ansible projects to encapsulate functionality and ensure that tasks can be reused across multiple playbooks.

Standard Ansible Roles Folder Structure
bash
Copy
Edit
roles/
└── <role_name>/
    ├── defaults/            # Default variables for the role
    │   └── main.yml         # Default variable file
    ├── files/               # Files to be copied to managed nodes
    │   └── <file_name>      # Static files such as .conf, .tar files
    ├── handlers/            # Handlers for notifications (e.g., service restart)
    │   └── main.yml         # Handlers to restart services
    ├── meta/                # Metadata for the role
    │   └── main.yml         # Role dependencies, authorship information
    ├── tasks/               # Main tasks for the role
    │   └── main.yml         # Tasks to be executed by Ansible
    ├── templates/           # Jinja2 templates
    │   └── <template>.j2    # Configuration templates
    ├── tests/               # Tests for role functionality (optional)
    │   └── test.yml         # Playbook to test the role
    ├── vars/                # Variables specific to the role
    │   └── main.yml         # Role-specific variables (may override defaults)
    └── README.md            # Documentation for the role (optional)
Explanation of Each Directory/Folder:
defaults/:

Default variables for the role that will be used unless explicitly overridden.
Contains main.yml, which holds default values for the role's variables. These can be overridden by other sources (e.g., playbook, inventory).
Example: nginx_port: 80
yaml
Copy
Edit
# roles/nginx/defaults/main.yml
nginx_port: 80
files/:

Contains static files that will be copied to the target machines.
Files could include .conf files, archives, scripts, etc.
Example: nginx.conf
handlers/:

Handlers are special tasks that only run when notified by other tasks (e.g., restarting a service after a configuration change).
Contains main.yml with handler definitions.
Example: restart nginx if the configuration file changes.
yaml
Copy
Edit
# roles/nginx/handlers/main.yml
- name: restart nginx
  service:
    name: nginx
    state: restarted
meta/:

Contains metadata about the role. This includes role dependencies, platform-specific details, and authorship information.
main.yml is the default file for this.
Example: Defines any dependent roles.
Example: dependencies: - { role: common, some_variable: value }
yaml
Copy
Edit
# roles/nginx/meta/main.yml
dependencies:
  - { role: common }
tasks/:

Main tasks that the role performs. These tasks could install software, configure services, etc.
The main.yml file in this directory contains the tasks to be executed.
Example: Install Nginx and start the service.
yaml
Copy
Edit
# roles/nginx/tasks/main.yml
- name: Install nginx
  apt:
    name: nginx
    state: present

- name: Start nginx service
  service:
    name: nginx
    state: started
templates/:

Contains Jinja2 templates used to generate configuration files for services or other software.
Example: A configuration file for Nginx that gets rendered with dynamic variables (like port numbers).
nginx
Copy
Edit
# roles/nginx/templates/nginx.conf.j2
server {
    listen {{ nginx_port }};
    server_name {{ server_name }};
}
tests/ (Optional):

Contains a test playbook to ensure the role works as expected.
You can test the role in isolation to verify its correctness before deploying it in production environments.
Example: A test.yml playbook to apply the role to localhost.
yaml
Copy
Edit
# roles/nginx/tests/test.yml
- name: Test nginx role
  hosts: localhost
  roles:
    - nginx
vars/:

Contains role-specific variables that are typically used to customize the role's behavior.
These variables override the defaults if necessary.
Example: Set a custom port for Nginx.
yaml
Copy
Edit
# roles/nginx/vars/main.yml
nginx_port: 8080
server_name: example.com
README.md (Optional):

A documentation file for the role that describes its purpose, usage, and variables.
Example Role: nginx
Here’s how the folder structure would look for an Nginx role:

bash
Copy
Edit
roles/
└── nginx/
    ├── defaults/
    │   └── main.yml         # Default variables (e.g., nginx_port: 80)
    ├── files/
    │   └── nginx.conf       # Static files to copy (nginx.conf)
    ├── handlers/
    │   └── main.yml         # Handlers for restarting Nginx
    ├── meta/
    │   └── main.yml         # Role metadata
    ├── tasks/
    │   └── main.yml         # Main tasks (install nginx, start service)
    ├── templates/
    │   └── nginx.conf.j2    # Template for Nginx config file
    ├── tests/
    │   └── test.yml         # Test playbook for Nginx role
    ├── vars/
    │   └── main.yml         # Variables (e.g., custom nginx_port)
    └── README.md            # Documentation about the nginx role
Using the Role in a Playbook
Once the role is structured, you can use it in a playbook like this:

yaml
Copy
Edit
---
- name: Configure web server
  hosts: web_servers
  become: yes
  roles:
    - nginx
This way, roles are reusable and maintainable. You can include them in different playbooks across multiple projects.

Would you like help creating an example role or applying this structure to a specific task?



-----EX:
https://github.com/praveen1994dec/Ansible/blob/main/create_user.yml

#
#About: This will create-user
#
---
- hosts: 'localhost'
  become: yes
  roles:
  - create-user

https://github.com/praveen1994dec/Ansible/blob/main/roles/create-user/tasks/main.yml

---
- name: set group with name shadow
  group:
   name: shadow

- name: set group with name sudo
  group:
   name: sudo
  
- name: Adding new user
  user: name=devops groups=sudo,shadow shell=/bin/bash append=yes generate_ssh_key=yes ssh_key_file=.ssh/id_rsa
  tags:
    - create-user


- name: Adding public key to authorized_keys
  file: src=/home/devops/.ssh/id_rsa.pub dest=/home/devops/.ssh/authorized_keys state=link
  tags:
    - create-user-authorized-keys

- name: Get the private key
  shell: cat /home/devops/.ssh/id_rsa
  register: ssh_key
  tags:
    - create-user-display-keys

- debug: var=ssh_key
  tags:
    - create-user-display-keys



---------------------
Handlers


==========================================================================================================
                                     RED HAT



cd /etc/yum.repos.d/

NMCLI- NetworkManger command line interface
- Ip adrress
- subnets
- cidrs (class less inter domain routing)
- dns
- route configurations
- ethernet cards and ports
- DHCP



SELINUX









