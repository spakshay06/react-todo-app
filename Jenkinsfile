pipeline {
    agent any
 
    stages {
       stage("Checkout") {
            steps {
               //added my github in the jenkins scm
                checkout scm
            }
        }
        stage("Install and Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
    }
} 

