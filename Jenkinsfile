pipeline {
    
    agent any
    
    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir() // wipes the workspace completely
            }
        }
        stage('Build') {
            agent{
                docker{
                    image 'node:22.6.0-alpine'
                }
            }
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
        stage('Test2'){
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