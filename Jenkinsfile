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
			sh 'mvn deploy'
            }
	   }
    }

}