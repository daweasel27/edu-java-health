pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B clean package'
            }
        }
		stage('artifact') {
			steps {
				archive 'target/*.war'
            }
	   }
	   stage ('deploy') {
		steps {
			echo 'deployment starte1d'
			sh 'sudo cp /var/lib/jenkins/workspace/PipelineHealth/target/health.war /opt/tomcat9/webapps'
            }
	   }
    }

}