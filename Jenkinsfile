pipeline{
    agent any
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/nimbuswiztech/maven_webapp.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
       stage('deploy'){
            steps{
                sshagent(['tomcat']) {
                    sh "scp -o StrictHostKeyChecking=no target/demo.war ubuntu@34.229.15.246:/opt/tomcat/webapps"

                }
            }
        }
       
    }
}
