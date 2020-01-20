pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
        stage('Deliver'){
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finish using the web site (Click "Process" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}