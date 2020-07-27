node {
    def mvnHome = tool 'maven'
    stage ("SCM checkout")  {
     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Shilpa0896/JavaMaven.git']]])
    }
    
     stage ('build')  {
    sh "${mvnHome}/bin/mvn clean package"
    }
     
    
    stage ('Code Quality scan')  {
       withSonarQubeEnv('sonar-server') {
       sh "${mvnHome}/bin/mvn sonar:sonar"
        }
   }
   
   stage('nexus upload'){
       nexusArtifactUploader artifacts: [[artifactId: 'maven', classifier: '', file: '/var/lib/jenkins/workspace/ScriptedPipeline/target/maven-1.0.0.jar', type: 'jar']], credentialsId: 'Nexus', groupId: 'sample', nexusUrl: '3.21.98.199:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'myrepo', version: '1.0.0'
        }
   }

   
