pipeline {
    agent any 
    stages {
        stage('git') { 
            steps {
                git "https://github.com/Shilpa0896/JavaMaven.git"
            }
        }
        stage('Build') { 
            steps {
               withSonarQubeEnv('sonar-server') {
              sh 'mvn clean package sonar:sonar'
                 }
            }
        
      }
    }

