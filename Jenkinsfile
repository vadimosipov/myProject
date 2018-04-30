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
                sh 'export PATH=$MAVEN_HOME/bin:$PATH && mvn clean compile'
            }
        }
        stage('test') {
            steps {
                sh 'export PATH=$MAVEN_HOME/bin:$PATH && mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'export PATH=$MAVEN_HOME/bin:$PATH && mvn package'
            }
        }
    }
}
