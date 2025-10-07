pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/<repo-name>.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build || echo "No build script"'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test || echo "No test script"'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: '**/*', onlyIfSuccessful: true
            }
        }
    }
}
