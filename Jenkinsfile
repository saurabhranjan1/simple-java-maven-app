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
                sh 'mvn sonar:sonar   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=acaf823d7f14d58f83ada7dc8acf283a170b9061'
            }
        }
	stage('Packaging Code'){
            steps {
                sh 'mvn package'
            }
        }
    }
}
