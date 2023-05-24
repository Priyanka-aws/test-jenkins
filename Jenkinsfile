pipeline {
    agent {
        docker { image 'node:10.16.3' }
    }
    stages {
        stage('Build') {
            steps {
               sh 'npm install'
            }
        }
        stage('Test') {
            steps {
               sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
               sh 'npm run deploy'
            }
        }
    }
}
