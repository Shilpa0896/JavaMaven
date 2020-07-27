pipeline{
    
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Shilpa0896/JavaMaven.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Clean Build'
                sh 'mvn clean package'
            }
        }
 }
}
