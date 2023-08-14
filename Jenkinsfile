pipeline {
    agent {
        docker { image 'node:lts-buster-slim' }
    }
    stages {
        stage('build') {
            steps {
                sh 'npm build'
            }
        }
    }
}