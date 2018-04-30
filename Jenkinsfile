pipeline {
    agent { label 'linux' }
/*
    tools {
        maven 'M3'
    }    
*/
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/vadimosipov/myProject.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
