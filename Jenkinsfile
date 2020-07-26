pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout'
            }
        }
        stage('Build') {
            steps {
                echo 'Clean Build'
                bat 'mvn clean compile'
            }
        }
        stage("code quality"){
     def scannerhome=tool "sonar-scanner";
    withSonarQubeEnv('sonar-server') {
        sh 'mvn clean package sonar:sonar'
    }
    }
