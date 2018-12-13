pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
        }
    }
    stages {
        stage('Clean Workspace') { 
            steps {
                sh 'mvn clean' 
            }
        }
        stage('Code Quality Analysis') {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
        }
	stage('Packaging Code'){
            steps {
                sh 'mvn package'
            }
        }
    }
}
