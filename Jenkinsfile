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
                sh 'sudo chmod +x ./jenkins/scripts/test.sh'
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