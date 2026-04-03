pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                bat 'set CI=false && npm test -- --watchAll=false'
            }
        }
    }
}