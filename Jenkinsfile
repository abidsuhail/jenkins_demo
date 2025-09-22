pipeline {
    
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:22.6.0-alpine'
                }
            }
            steps {
                sh '''
                   sudo npm i netlify-cli -g
                   netlify --version
                '''
            }
        }
    }
}