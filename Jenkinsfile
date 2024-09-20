pipeline {
    agent any
    tools {
        nodejs 'nodejs'
    }
    stages {
        stage("Checkout") {
            steps {
                // Checkout the code from your repository
                checkout scm
            }
        }
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
    }
}
