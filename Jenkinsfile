
pipeline {
    agent any
    stages {
        stage("Checkout") {
            steps {
                // Checkout code from your repository
                checkout scm
            }
        }
        stage("Build") {
            steps {
                // Install npm dependencies
                sh "npm install"

                // Build the application
                sh "npm run build"
            }
        }
        stage("Serve Build") {
            steps {
                // Install http-server globally
                sh "npm install -g http-server"

                // Serve the build folder using http-server
                sh "http-server build -p 8080 &"

                // Print the URL where the site is served
                echo 'Your site is being served at http://localhost:8080/'
            }
        }
    }
    post {
        always {
            // Ensure the workspace is cleaned up
            cleanWs()
        }
    }
}
