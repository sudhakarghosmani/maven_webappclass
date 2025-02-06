pipeline {
    agent any
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages {
        stage('GetCode') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/sudhakarghosmani/maven_webappclass'
            }
        }        
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
    }
}
