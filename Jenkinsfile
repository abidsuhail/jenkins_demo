pipeline {
    agent{
        docker{
            image 'node:22.6.0-alpine'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                   ls -la
                   node --version
                   npm --version
                   npm ci
                   npm run build
                   ls -la
                '''
            }
        }
        stage('Test'){
            steps{
                sh '''
                test -f dist/index.html
                '''
            }
        }
    }
}