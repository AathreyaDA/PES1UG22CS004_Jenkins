pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/AathreyaDA/PES1UG22CS004_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS004-1 main.cpp'
            }
        }
        stage('Test') {
            steps {
                sh './PES1UG22CS004-1'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
