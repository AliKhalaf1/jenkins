pipeline {
    agent anay
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
        stage('dockerbuild') {
            steps {
                sh 'docker build -t node:lts-buster-slim'
            }
        }
    }
}