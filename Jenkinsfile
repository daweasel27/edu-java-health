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
		stage('artifact') {
			steps {
				archive 'target/*.war'
            }
	   }
	   stage ('deploy') {
		steps {
			echo 'deployment started'
			sh 'cp /var/lib/jenkins/workspace/PipelineHealth/target/health.war /opt/tomcat/webapps/'
            }
	   }
    }

}