pipeline {
    agent any
    stages {
         stage('Clone repository') {
             steps {
                 checkout([$class: 'GitSCM',
                 branches: [[name: '*/main']],
                 userRemoteConfigs: [[url: 'https://github.com/ankitkumar099/PES2UG22CS076_Jenkins.git']]])
             }
         }

        stage('Build') {
            steps {
                build 'PES2UG22CS076-1'
                sh 'g++ newfile.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './ot'
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
