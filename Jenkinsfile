pipeline {
    agent {
        node {
            label 'built-in'
            customWorkspace 'C:\\jenkins\\kyrian'
        }
    }

    environment {
        NETLIFY_SITE_ID = '319bb896-dfb6-4997-9eba-8d1560b6d332'
        NETLIFY_AUTH_TOKEN = credentials('netlifyToken')
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

        stage('Deploy') {
            steps {
                bat 'npm install netlify-cli'
                bat 'node_modules\\.bin\\netlify deploy --prod --dir=build --auth=%NETLIFY_AUTH_TOKEN% --site=%NETLIFY_SITE_ID%'
            }
        }
    }
}