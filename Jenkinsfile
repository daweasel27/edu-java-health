pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/daweasel27/edu-java-health'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B package'
            }
        }
    }
}