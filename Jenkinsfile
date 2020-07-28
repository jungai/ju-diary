pipeline {
    agent {
        docker {
            image 'node:12.16.3-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Lint') {
            steps {
                sh 'yarn lint'
            }
        }
    }
}
