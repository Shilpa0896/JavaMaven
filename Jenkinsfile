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
                sh"mvn clean package" 
            }
        }
        
    }
}
