### intruduction about jenkins
-----------------------------
- linux services also called as daemon
- 
- Install
  - sudo apt cache madison openjdk-17-jdk
  - sudo apt update
 ```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
  - sudo systemctl status jenkins.service
  - 
# Date: 16-07-2022
  - fast api
  - Dependencies
    - dotnet - nuget
    - java - maven
    - python -pip
    - node js - npm
                  - spring framework --spring boot (depencies to java)
    - artifacts
    - unit test
    - code coverage
    - static code analysis
    - artifaact repository
    snap shot --using to indicates product devopment under process
   - maven
    - configuration -early
    - conventions -now
    - gradelling -- android
    - 
    - log4j vulnerabilities
    - artifact repositries
  - sample maven vm 
  - install java 17
  - sure files - test case results
  - model version - maven structure defined by its 
  - group id -organization indicates
  - pom -- package object model
  - .m2 ///

  - exercize:
    - freestyle -- ui
    - pipeline -- cli 
      - scrpited pipeline
      - declarative pipeline
      -
      http://34.136.206.236:8080/
      - 
  - Big- BAng Theory:
  ------------------
  - presentation layer >>business layer >>Data Layer
  - Web Develop team >> Develop Team >> Data Layer Team
  - sun micro systems -- hud-sun
  - Cloud bees --kohsuke kawaguchi >>
  - toyoto >> regular interval releases done by toyota
  - reduce time to market
  - frequent release
  - its ok to fail 
  - DevOps invented ---Dev + Ops
  - continues area (feature flex)
  
 - cronjob linux (*/1 * * * * /tmp/pinggoogle.sh ) 
 - task scheduler -windows
 - 
### Jenkins installation on ubuntu
----------------------------------
```
- sudo apt update
-  sudo apt install openjdk-17-jdk
-  curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
-  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
- sudo apt update
- sudo apt-get install jenkins
- java --version
- sudo systemctl status jenkins.service
- sudo cat /var/lib/jenkins/secrets/initialAdminPassword
``` 
- open port on ip:8080
- suggested plugins
- crate user 
- 

use bash script understands crontabwork
```
#!/bin/bash
ping -c 4 google.com
pwd
whoami
```

---Login jenkins 
  - creat schedule by using con tab 
    - new item
       - freestyle project
         - source code management
         - pool scm
      - build steps 
       - execute shell
       check result over 
    - Dashboard
concept
#1
Console Output

------
jenkins workspace :  /var/lib/jenkins/workspace/concept
configure name of the job >> edit the script 

-- with out giving permission to jenkins user we cant do all works which ubuntu done
- permission to jenkins user
----------------------------
- cat /etc/passwd
- jenkins:x:109:115:Jenkins,,,:/var/lib/jenkins:/bin/ba(jenkins user location)
- log in root user (sudo -i )
- vi sudo 
- jenkins ALL=(ALL:ALL) NOPASSWD:ALL
- then again build which can be run on sudo user it will be run
- Install something on jeniks user
----------------------------------
-  sudo -i 
- su jenkins
- sudo apt update
- sudo apt install maven -y

git spc:
-------
manual :
- log in to jenkins user 
- change directory cd/tmp
- git clone https://github.com/spring-projects/spring-petclinic.git
- cd spc
- mvn package

from jenkins:
- create new item
- source code management copy https://github.com/spring-projects/spring-petclinic.git
- branch change and
- build steps mvn package

jenkins plugins:
--------------
- plugins add functionality to jenkins -- simplification convert to low lever commands
- not to the system

node concepts:
-------------


Path Variables:
--------------
- mkdir scripts
- cd scrpits (/home/dell/scripts)
- vi pinggoogle.sh
- cd ~
- try to execute
- pinggoogle.sh (comand not found)
-  sudo vi /etc/environment
- source /etc/environment
- vi ~/.bashrc

-- compiler and interpretor:
----------------------------
- complier : before (python nodejs ,c,c++,go)
- interpetor : translater while working 
         C# >> IL           >>>              OS
         JAVA>> Byte code   interpreter
  hybrid approch

Depencdecies:
------------
- dependencies have to available before build 
- manage dependecies we need package manger
   - .net (nuget) (packages.config or packages.json)
   - java (maven) 
   - python: pip
   - nodejs : npm
  
Artifacts: saved the packages build tools : mvn/gradle  
unit tests: py.test (write code and test code)  junit:java ,jasmine,mocha ...formate xml 
code coverage: its depends on the code 
      if commands intervert the code those are worked :sonar cube
  we can use those b/w these 
static code analysis: sonar cube
artifact repository: aws //azure//jfrog


- git the code version control system
- build the code to generate artifact
- run unit tests
- generate code covarage test and report
- run the static code analysis 
- code quality report

quality gate: check the metrics to meet the expectation

- Maven:
--------
- Maven Dependecies
- Build package distribute test generate documentaion 
- java && java based
- (log4j)--- 


Maven installation:
--------------------
```
sudo apt update
sudo apt install openjdk-17-jdk -y
<< mvn link `https://dlcdn.apache.org/maven/maven-3/3.9.3/binaries/apache-maven-3.9.3-bin.tar.gz`>>
cd /tmp
wget https://dlcdn.apache.org/maven/maven-3/3.9.3/binaries/apache-maven-3.9.3-bin.tar.gz
sudo mkdir /usr/share/maven
sudo tar -xvxf apache-maven-3.9.3-bin.tar.gz -C /usr/share/maven
cd /usr/share/maven
cd apache-maven-3.9.3/
cd bin/
 ./mvn --version
`Apache Maven 3.9.3 (21122926829f1ead511c958d89bd2f672198ae9f)
Maven home: /usr/share/maven/apache-maven-3.9.3
Java version: 17.0.7, vendor: Private Build, runtime: /usr/lib/jvm/java-17-openjdk-amd64
Default locale: en, platform encoding: UTF-8
OS name: "linux", version: "5.19.0-1027-gcp", arch: "amd64", family: "unix" `
sudo vi /etc/environment (or) ./bashrc
PATH=/usr/share/maven/apache-maven-3.9.3/bin
source /etc/environment
dell@mvn:~$ mvn -version
Apache Maven 3.9.3 (21122926829f1ead511c958d89bd2f672198ae9f)
```
* validate: validates the pom and its project
* compile: this converts the java code into byte code (.java to .class). It stores the class files in target/classes
* test: it will run the unit tests written and generates test results in xml format in text format. folder will be /target/surefire-reports/TEST-*.xml
* package: This creates the packaging format (jar/war/ear). will be <artifact-id>-<version>.<packaging-format>
* install: This copies the package and its definition into M2_HOME or ~/.m2/repository
* deploy: copying package and its definition to remote repository for other users in other systems to use what you have built
* clean: clean removes target folder

Information About Jenkins:
-------------------------
- sudo -i 
- su jenkins
- cd ~
- pwd (/var/lib/jenkins)

- JENKINS_HOME: where jenkins store all of configuations `/var/lib/jenkins`
- if we want change the workspace of jenkins env varible `JENKINS_HOME`
- Backup: backup of floder `/var/lib/jenkins`
- project (job): this contains that needs to be perfermed on triggers
- stored as xml file
  - types of project:
    - freestyle project: this is ui based configuration
    - 
- Build: this represents the execution of project stage.every build have build id
- Node: Machine which can be executed
  - each node can be configure to handle multiple builds by executers.
  - parlally 2builds can execute
pipeline: this is instructions expressed in some code formate

General : this represents the project info
Source Code Managent: This represent the code to be used for ci/cd pipelines
Build Triggers: This represent when to build
Build Periodically: If the project has to be build based on schedule, write cron expression into this Refer Here
Poll SCM: this represents jenkins polling scm (asking git) and the cron expression represents how frequently should it ask
Build Environment: This represents the environmental configuration
Build Steps: These are actual activities that are performed during execution.
Post Build actions: Actions to be performed after completion of build
`target/surefire-reports/TEST-*.xml`

Using Jenkins to Build Maven Projects: spring petclinic
-------------------------------------
- sudo apt install maven
- cd ~
- jobs/spc-daybuild/
- config.xml infor
- error (mvn -f path/to/pom.xml <goals> ...)
- /var/lib/jenkins/jobs
- /var/lib/jenkins/workspace/

setup maven version in tools:
----------------------------
- open manage jenkins 
- open tools
- add maven version at maven invoke build steps
- MAVEN_3.6 >>path /usr/share/maven/ set version and path 
- MAVEN_3.9 >> path /usr/share/maven/apache-maven-3.9.3 set path 

Distributed Builds: fork all the repos in our github
------------------
- spc
  - java 17
  - maven 3.9
- gol
  - java 8
  - maven 
- nop
  - dotnet 7

script for install jenkins:
----------------------------
- create a file install jenkins.sh >>> vi installjenkins.sh
paste the script file 
```
#!/bin/bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install openjdk-17-jdk jenkins -y
```
- run the file >> ./installjenkins.sh
- sudo apt install openjdk-17-jdk
- chmod +x installjenkins.sh


Configuration of Master and Node: SPC
-------------------------------
- on master node install jenkins and configure
- on node 1 (Spc)
  - install java 17
  - install maven 3.9.3
  - configure node1 to master label `JDK-17`
  - manage jenkins >> nodes & clouds >> New node
  - configure and name >>node-1 
  - now download git repos of spc wich we are forked
  - PROJECT >>spc-day1-build >> configure all the changes 
  - Restrict where this project can be run
  - JDK-17
  - give our repostory which are forked in >> scm
  - poll scm >> * * * * * 
  - Invoke top-level Maven targets >>> Goals >> package
  - check console out put
  - manually check file location on node- 1(~/jenkins_root/workspace/spc-day1-build$)
  - ip addr (it will show the ip address)
  - print env
  - **/target/spring-petclinic-*.jar
  - Last Successful Artifacts
spring-petclinic-3.1.0-SNAPSHOT.jar

Configuration of Node2 : Gol
---------------------------------------
- sudo adduser somanath
- sudo visudo
- sudo vi /etc/ssh/sshd_config >>> pw aus >>>yes
- sudo systemctl restart sshd
- sudo apt update
- sudo apt install openjdk-8-jdk openjdk-17-jdk -y
-  java -version ( openjdk version "17.0.7" 2023-04-18 )
-  where is java
-  find java path (/usr/lib/jvm)
- sudo apt install maven
- maven --version
- Add Jdk version toll section in jenkins:
- find the both java versions 
  - JDK_8 >> /usr/lib/jvm/java-17-openjdk-amd64
  - JDK_17 >> /usr/lib/jvm/java-8-openjdk-amd64
- Configure node2 on manage jenkins>> nodes and clouds
- sleect project and configure jdk && maven version and git clone game oflife 
- save && Build
- reports saved location (/home/somanath/jenkins_root/workspace/gameoflife/gameoflife-web/target/surefire-reports)
- folder saved (/home/somanath/jenkins_root/workspace/gameoflife/gameoflife-web/target/gameoflife.war)
- Disable Project
Test Result Trend
Last Successful Artifacts
gameoflife.war (Downloded)

Configuration of Node3: NOP
----------------------------
- sudo apt-get update && \
- sudo apt-get install -y dotnet-sdk-7.0
-  dotnet --version
7.0.109
- restore nuget packages
- dotnet restore src/NopCommerce.sln
- git checkout
- sudo apt install openjdk-17-jdk -y
- configure nodes and clouds >>> node-3 agent 
- 
Upstream and Down Stream Projects Configuration:
----------------------------------------------
- Eg : A >> B >> C  ( for B ,, A is the upstream proj C is the downstream proj)
- based on the status use triggers
- after job finish use post build actions

Parameterized Builds:
---------------------
- pass some inforamtion while build project >>called as parameterizes builds
- choice parameter (write the choices)
- $GOAL use where build steps 
- ui has changed
- build with parameter
- we can select what we are mentioned choices

Jenkins Environmental variables
-------------------------------
- jenkins logically added some env varibles to understand
- any project See the list of available environment variables
- 
Backup Jenkins
--------------
- Add plugins - Managejenkins >> plugins >> 
  - Peridic manager 
    - check confiuration and configure back up use plugin
- Copy of /var/lib/jenkins >> store some where else
- install with out restart use to restart when no jobs running

Jenkins Monitoring
------------------
- plugins for moniter the jenkins
- we can check in monitor plug in ins manage jenkins

Build number && Id plugins 
---------------------------
- JPI (jenkins plugin interface)
- HPI (Hud-sun plungin interface)
- No projects (is equal to no executers)

Maintaing history in jenkins by using git: pipe line as a code (jenkins dsl)
-----------------------------------------
- craete a folder understanding git versioning and history maintainance
- create git repo
   - create 3 banches as
     - master 
     - develop
     - release

- in gui based CI/CD tools we cant maintain history 
- that the cause we are using pipe line as code we have vcs systems maintain hostory

### PIPELINE AS CODE:
---------------------

Script Based Pipeline:
---------------------
-  sample Azure file understanding 
```
trigger:
- main
pool:
  name: Default
steps:
  - task: Maven@3
    inputs:
      mavenPOMFile: 'pom.xml'
      goals: 'package'
      publishJUnitResults: true
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
      testRunTitle: 'unittests'
```
Scripted pipe line understanding:
```Jenkinsfile
node("JDK-17-MVN") {
  stage("get-code") {
    sh " git clone https://github.com/spring-projects/spring-petclinic.git && cd spring-petclinic"
  }
  stage("build") {
    sh "mvn package"
    junit '**/surefire-reports/TEST-*.xml'
  }
}

```
- groovy is the software jenkins mostly depend on this scripted based pipeline
- if project depends of several stages involved used scripted
- it will executeed groovy language
- 
Gameoflife scripted pipeline:
----------------------------
- Jenkins has Create a DSL (Domain Specific Language) inspired from traditional
- straight-forward ways used declarative
- view/Scripted/job/gameoflife-scriped-pipeline/pipeline-syntax/
```
- node('JDK_8') {
    stage('git') {
        git branch: 'master', url: 'https://github.com/SHIVASOMANATH/game-of-life-m.git'
    }
    stage('build') {
        sh 'mvn package'
    }
    stage('reporting') {
        archiveArtifacts artifacts: 'gameoflife-web/target/gameoflife.war', followSymlinks: false
        junit '**/surefire-reports/TEST-*.xml'
    }
}
```

Declarative --Pipelines CLI: 
----------------------------
-  jenkinsfile 
``` Jenkinsfile
pipeline {
    agent {label 'JDK_17'}
    stages {
        stage('git') {
            steps{ 
                git branch: 'main', url: 'https://github.com/SHIVASOMANATH/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
``` 
Writing Pipeline using documention (Jenkins):
--------------------------------------------
```Jenkinsfile
pipeline {
    agent { label 'JDK-17' }
    options {
        timeout(time: 1, unit: 'HOUR')
    }
    triggers {
        pollSCM(* * * * *)
    }
    tools {
        jdk 'JDK_17'
        maven 'MAVEN_3.9'
    }
    stages {
        stage ('VCS') {
            steps {
                git url: 'https://github.com/SHIVASOMANATH/spring-petclinic.git',
                    branch: 'develop'
            }
        }
        stage ('Build and Package') {
             steps {
                 sh script: 'mvn package'
            }     
        }
        stage ('Reporting') {
             steps {
                archiveArtifacts artifacts: '**/target/springpetclinic-*.jar'
                junit testResults: '**/target/surefire-reports/TEST-*.xml'
            }
        }
    }
}
```
- environmental varible used for ssh keys user name pw 

Mailtrap:
---------
- setting up mail trap using with outllok mail
- managejenkins >> SMTP server
- SMTP server
sandbox.smtp.mailtrap.io
Default user e-mail suffix
?
Advanced
Edited

Use SMTP Authentication
?
User Name
c4b2753a76f904
Password
••••••••••••••

Use SSL
?

Use TLS --yes
SMTP Port --587
?
- Test configuration by sending test e-mail
- shivasomanath7@outlook.com
Email Notification:
-------------------
- Lets send an email
  - project fail : 'your project diffective'
  - project success: 'msg is affevctive'
  post function return for notification mail
  ```
      post {
        success {
            mail subject: 'your project is affective'
                 body: 'working'
                 to: 'all@qts.com'
        }
        failure {
            mail subject: 'your project is Defective'
                 body: 'not working'
                 to: 'all@qts.com'     
        }
    }
  ```
- click on replay on build number
- send notification several system msg services eg : team,slack etc...
- add environmental varibles over here information JOB_URL,,etc...
- use "" pass environmental varible
- emailext--try
Parameters:
----------
```
-     parameters {
        choice(name: 'GOAL', choices: ['package','clean package','install','clean install'],
         description: 'This is Maven Goal')
    }
    stages {
        stage('source code') {
            steps {
                git url: 'https://github.com/SHIVASOMANATH/game-of-life-m.git',
                    branch: 'master'
            }
        }
        stage('package') {
            steps {
                sh script: "mvn ${params.GOAL}"
            }
        }
    }
```
User Administration in Jenkins:
------------------------------
- Dashboard >> Manage Jenkins >>Security
- LDAP: Active Directory inforamtion
 - creating 
   - user 
   - groups 
      - understanding permission gave to user and groups
      - called as Matrix based security
create user as dummy-
  -  Dashboard >> Manage Jenkins >>enkins’ own user database

  plugins:  -role based authorization stratagy
  - Matrix Based
configure role based through availble plugins 

  - folder based
  - project based 
  
  permissions : authorization & authontication

Maven Remote Repos:
------------------
- local repo (~/.m2)
- remote repo (this is public maven repo)
- central repo (this is organized entrolled env)

- after every neghit build 
- eg : jrog,, azure repos,Nexus

JFROG INSTALLATION: one of the remote repository
-------------------
- give google credential to create jfrog
- go with ci tools
- save the credentials after create repo
- https:///artifactory/api/maven/somanathjenkins-libs-snapshot
- create token 
- cmVmdGtuOjAxOjE3MjIwODQyMjE6UXVtTWl1NVNSTHB5U2FuZmw5eGZxY1UzUnNX
- managejenkins >> plugins >> availble plugins >> jfrog
- Dashboard >>Manage Jenkins>> System >> Add jfrog platform instance
- Dashboard>>Manage Jenkins>>Credentials>>System>>Global credentials (unrestricted)
- https://somanath2023.jfrog.io/artifactory/api/maven/shiva_jenkins-libs-snapshot
- snapshot -- is the convention for project under process
- release -- project finished 
- jenkins acceess token
- eyJ2ZXIiOiIyIiwidHlwIjoiSldUIiwiYWxnIjoiUlMyNTYiLCJraWQiOiJRM2thNFB3VHVvSWs2STJ1amFtVDRUWWxKbTh2YlNQZ3VjQmQtam83N3RzIn0.eyJzdWIiOiJqZmFjQDAxaDZlMWd3NWhnbWFhMXF3OWFmZzYxanpwL3VzZXJzL2plbmtpbnNzaW5rIiwic2NwIjoiYXBwbGllZC1wZXJtaXNzaW9ucy9hZG1pbiIsImF1ZCI6IipAKiIsImlzcyI6ImpmZmVAMDFoNmUxZ3c1aGdtYWExcXc5YWZnNjFqenAiLCJleHAiOjE2OTMyMDcxNTUsImlhdCI6MTY5MDYxNTE1NSwianRpIjoiZGVhYjQ1MGQtMWE1Mi00NjZhLWE5MDQtMzI1ZjU5YzY4MmIzIn0.W6IBtu1AhYHJ51JRGkII98TosgJlp5ZH6WQF9zimdJzyEG0FDJLqnGdTfba4YkpERhX8YizkFek9rZtCg_DoQpR2bOV-mPn_Rs68cbb62d0jjCX23ZRZeQGi2emw9th58Ji1dZSTdfNN2-wgsGOkd5MRPn_YUic17iZO7fSmAYhr_pXlxcFETA4SaUGRVdeeMmGs0u1HcRiHgg_LRdzxpWzcESYy5hf7DPEeWF77-BG_7IHBlm0mi08X24Ug9GsmHor4nVa1UrG9NAhJq3UDd0vgH1Oi_bMGbuHwQjnqKo4U0OkV0bFzKWFneZ9mEShWuKkzdzPEUQmKBwn40nEeew
- url 
- https://somanath2023.jfrog.io
- create credentials >> secret key
- 
Use the Credentials Plugin
- now we can see maven project >> new item 
- which are configured by jfrog
- Resolve artifacts from Artifactory //use when u are subbmited ur repo in jfrig then we can use
- post build action >> deploy artifact to artifactory
- 
jfrog pipeline 
```pipeline 
  stage ('Jfrog Artifactory Configuration') {
       steps {
          rtMavenDeployer (
              id: "SPC_DEPLOYER",
              serverId: "JENKINS__JFROG_SHIVA",
              releaseRepo: 'shiva_jenkins-libs-snapshot-local',
              snapshotRepo: 'shiva_jenkins-libs-snapshot-local'
          )
          rtMavenRun (
              tool: "MAVEN_3.9",
              pom: "pom.xml", 
              goals: "clean install",
              deployerId: "SPC_DEPLOYER"
              //,
              //buildName: "${JOB_NAME}",
              //buildNumber: "${BUILD_ID}"
          )
          rtPublishBuildInfo (
              serverId: "JENKINS__JFROG_SHIVA"
          ) 
      }
  }    
```

- configure with system >>Managejenkins
- and execute with freestyle and pipeline 
- find the way of work by looking pipeline syntax

## Static Code Analysis:
------------------------
- Sonar cloud Or sonar cube installation
- 7427c1924e2cdc701360b70bfb84463f0cadc92d --sonar pat
- 




Git branching stratagy:
----------------------
  - git hub
  - git lab
- artifacts mostly build in store when night builds relese branch jfrog
- 


  hotfix branch >> mostely manually fixes and full permissions will give to it is happend un expeted situvations

- Master Branch
  - no one can do work on master branch untill release code
- Develop Branch 
  - no on have permission to work on this 
     created feature branches 
  - to do work on the code &  given permission 
  - when we add code to merge to develop branch we need to build the code and anlayis the test if it failes not allowed to merge or add the code 
  - when the developer create pull automatically build has bee trigger 
  - 


>> Master (ALL CLEAR) 
>> Hot fixes ( manual unexpected things full permission)
>> RELEASE ( DAY BUILD (TEST)/ NEIGHT BUILD(ARTIFACTORY))
>> Develop ( fork >> 
   >> feature branch --work
   Reverse 
   >> pull request >> ci trigger >> ci start test pass
   develop branch ) 
   >> develop branch >> day build >> release
   >> release branch >> tester ( bug fixes) >> Master branch

Pull -Request:activities
-------------
- trigger 
 - pr
- develop >> sprint
- release branch >> sprint release
- before pull request
- day build
- night build



narsigarao //naresh sir
9154191654 --- busy