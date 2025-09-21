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
                   pwd
                   node --version
                   npm --version
                   npm ci
                   npm run build
                '''
            }
        }
        stage('Test'){
            steps{
                sh '''
                pwd
                test -f dist/index.html
                '''
            }
        }
    }
}