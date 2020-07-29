pipeline {
    agent {
        docker {
            image 'node:12.16.3-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
      SERVER_IP = credentials('SERVER_IP')
    }
    stages {
        stage('Initial ....') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Linting ....') {
            steps {
                sh 'yarn lint'
            }
        }
        stage('Deploy Runtest ....') {
          echo "${env.JOB_NAME}"
          echo "target server -> ${SERVER_IP}"
        }
    }
}
