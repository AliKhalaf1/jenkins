pipeline {
     agent {
        docker { 
            image 'node:lts-buster-slim'
            args '-v /var/run/docker.sock:/var/run/docker.sock' 
            args '-v /usr/bin/docker:/usr/bin/docker'
             }
    }
    stages {
        stage('dockerbuild') {
            steps {
                sh 'docker build -t nodeapp:latest .'
            }
        }
 
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