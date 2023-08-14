pipeline {
    agent {
        docker { image 'node:lts-buster-slim' }
    }
    stages {
        stage('install') {
            steps {
                sh 'npm i'
            }
        }
        stage('bulid') {
            steps {
                sh 'npm run build'
            }
        }
        stage('test') {
            steps {
                sh 'npm run test'
            }
        }
    }
}