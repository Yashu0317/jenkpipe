pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Archive') {
            steps {
                bat 'powershell Compress-Archive -Path * -DestinationPath build.zip'
                archiveArtifacts artifacts: 'build.zip', fingerprint: true
            }
        }
    }
}
