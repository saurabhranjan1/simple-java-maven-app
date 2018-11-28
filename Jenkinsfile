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
	stage('Build'){
            steps {
                sh 'mvn compile'
            }
        }
	stage('Packaging Code'){
            steps {
                sh 'mvn package'
            }
        }
    }
}
