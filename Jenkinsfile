pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Yashu0317/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/*.zip', fingerprint: true
            }
        }
    }
}
