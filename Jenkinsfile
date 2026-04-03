pipeline {
    agent {
        node {
            label 'built-in'
            customWorkspace 'C:\\jenkins\\kyrian'
        }
    }

    stages {
        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test -- --watchAll=false'
            }
        }
    }
}