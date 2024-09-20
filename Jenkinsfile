pipeline {
     agent any
tools {
nodejs 'nodejs'
}

     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
}
