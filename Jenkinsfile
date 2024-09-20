pipeline {
    agent any

    tools {
        nodejs 'NodeJS 14' // Name of the NodeJS installation in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from the GitHub repository
                git branch: 'main', url: 'https://github.com/spakshay06/react-todo-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install' // Install project dependencies
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test' // Run tests (if any)
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build' // Build the React app
            }
        }

        stage('Deploy') {
            steps {
                // Example: Deploy to Firebase (Firebase CLI must be installed)
                withCredentials([file(credentialsId: 'firebase-token', variable: 'FIREBASE_TOKEN')]) {
                    sh '''
                    npm install -g firebase-tools
                    firebase deploy --token "$FIREBASE_TOKEN"
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'Build and Deployment Successful!'
        }
        failure {
            echo 'Build or Deployment Failed!'
        }
    }
}

