# Assignment maven-project.
 
Configured Maven application with Jenkins DSL Pipelines

Step1:- Pull Jenkins Image from Docker hub and run the container and install the plugin.

Step2:- Setup Java_Configuration
Step3:- Setup maven Configuration
step4:- create your pipeline job and after that go to 'Pipeline Script from SCM' and in Script path we set our Jenkinsfile path
Step5:- Clone the github repository with crenditails and we can take the help from generate pipeline syntax.
Step6:- Build code with mvn packages.
Step7:- Deploy on tomcat server(in this i have taken tomcat server from AWS)
Step8:- for connection tomcat to jenkins we configured ssh.
Step9:- start the tomcat.
