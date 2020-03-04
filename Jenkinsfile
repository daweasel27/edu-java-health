pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B package'
            }
        }
    }
	stage('artifact') {
      
      archive 'target/*.war'
   }
   stage ('deploy'){
		echo 'deployment started'
        sh 'cp /var/lib/jenkins/workspace/PipelineHealth/target/health.war /opt/tomcat/webapps/'
   }
}