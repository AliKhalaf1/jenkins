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
        stage('build') {
            steps {
                sh 'npm run build'
            }
        stage('tes') {
            steps {
                sh 'npm run test'
            }
        }
    }
}