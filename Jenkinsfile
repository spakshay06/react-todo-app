pipeline {
    agent any
    stages {
        stage("Checkout") {
            steps {
                checkout scm
            }
        }
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Install and Serve") {
            steps {
                // Install http-server locally (without -g)
                sh "npm install http-server"

                // Serve the build folder using http-server on port 3000 (or any other available port)
                sh "./node_modules/.bin/http-server build -p 3000 &"

                echo 'Your site is being served at http://localhost:3000/'
            }
        }
    }
    post {
        always {
            cleanWs() // Clean workspace after execution
        }
    }
}
