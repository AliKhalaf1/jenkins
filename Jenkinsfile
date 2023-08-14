pipeline {
     agent  none

    stages {

 
        stage('install') {
            agent {
                docker { image 'node:lts-buster-slim' }
            }
            steps {
                sh 'npm i'
            }
        }
        stage('bulid') {
            agent {
                docker { image 'node:lts-buster-slim' }
            }
            steps {
                sh 'npm run build'
            }
        }
        stage('test') {
            agent {
                docker { image 'node:lts-buster-slim' }
            }
            steps {
                sh 'npm run test'
            }

        stage('dockerbuild') {
            steps {
                sh 'docker build -t nodeapp:latest .'
            }
        }
        
        } 
    }
}