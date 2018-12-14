pipeline {
    agent none
    stages {
        stage('Clean Workspace') { 
            agent { docker 'maven:3-alpine' }
            steps {
                sh 'mvn clean' 
            }
        }
        stage('Code Quality Analysis') {
        agent none
            steps {
                sh 'mvn sonar:sonar   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=acaf823d7f14d58f83ada7dc8acf283a170b9061'
            }
        }
	stage('Packaging Code'){
        agent { docker 'maven:3-alpine' }
            steps {
                sh 'mvn package'
            }
        }
    }
}
