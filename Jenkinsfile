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
         sudo mv /var/lib/jenkins/workspace/Pipeline\ Health/target/health.war /opt/tomcat/webapps/
   }
}