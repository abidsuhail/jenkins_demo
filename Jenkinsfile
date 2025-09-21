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
                   npm ci
                   npm run build
                '''
            }
        }
    }
}