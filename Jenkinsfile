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
                   echo "🔹 This is the current workspace path:"
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
                echo "🔹 This is the current workspace path:"
                pwd
                test -f dist/index.html
                '''
            }
        }
    }
}