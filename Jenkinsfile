pipeline {
    agent {
        docker { image 'node:lts-buster-slim' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}