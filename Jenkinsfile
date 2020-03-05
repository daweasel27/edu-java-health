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
			sh 'mv /var/lib/jenkins/workspace/PipelineHealth/target/health.war /var/lib/jenkins/workspace/PipelineHealth/target/doctors.war'
			sh 'sudo cp /var/lib/jenkins/workspace/PipelineHealth/target/doctors.war /home/portodeloitte/Desktop/tomcat/webapps/api'
            }
	   }
    }

}