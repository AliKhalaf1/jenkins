pipeline {
     agent  any

    environment {
            USER_CREDENTIALS = credentials('docker_hub_account')
      } 

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
        }
        stage('dockerbuild') {
            steps {
                sh "docker build -t hossamalsankary/nodeappjana:${env.BUILD_ID} ."
            }
        }
        stage('pushing') {
            steps {
                sh "echo ${USER_CREDENTIALS_USR}"
                sh "echo ${USER_CREDENTIALS_PSW}"
                sh "docker login -u ${USER_CREDENTIALS_USR} -p ${USER_CREDENTIALS_PSW}"
                sh 'docker push hossamalsankary/nodeappjana:${env.BUILD_ID}  '
            }
        }        

        } 
    }

