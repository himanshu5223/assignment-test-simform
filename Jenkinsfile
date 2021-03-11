pipeline {
    agent any
    environment {
        PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
    }
    stages {
        stage("SCM"){
            steps{
               git credentialsId: 'git_credentials', url: 'https://github.com/himanshu5223/assignment-test-simform'
            }
        }
        stage("Build"){
            steps{
              sh "mvn clean install"
              sh "mv target/*war target/webapp.war
            }
        }
        stage("Deploy"){
            steps{
              sshagent(['deploy_user']) {
                 sh "scp -o StrictHostKeyChecking=no /target/webapp.war ec2-user@13.233.81.96:/opt/apache-tomcat-8/webapps"
                  ssh ec2-user@13.233.81.96 /opt/tomcat8/bin/shutdown.sh
                  ssh ec2-user@13.233.81.96 /opt/tomcat8/bin/startup.sh
                 
                }
            }
        }
    }
}
