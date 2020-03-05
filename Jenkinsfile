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
			sh 'mvn tomcat8:deploy'
            }
	   }
    }

}