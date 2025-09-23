pipeline {
    
    agent{
        docker{
            image 'node:22.6.0-alpine'
        }
    }

    environment{
        NETLIFY_SITE_ID = 'ea1c4fd9-b0b9-4502-8fd8-417d3b537af9'
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                   npm ci
                   npm run build
                '''
            }
        }
        stage('Deploy Staging') {
            steps {
                sh '''
                   npm i netlify-cli
                   node_modules/.bin/netlify --version
                   node_modules/.bin/netlify status
                   node_modules/.bin/netlify deploy --no-build --dir=dist
                '''
            }
        }
        stage('Deploy Prod') {
            steps {
                sh '''
                   npm i netlify-cli
                   node_modules/.bin/netlify --version
                   node_modules/.bin/netlify status
                   node_modules/.bin/netlify deploy --no-build --dir=dist --prod
                '''
            }
        }
    }
}