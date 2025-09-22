pipeline {
    
    agent any

    environment{
        NETLIFY_SITE_ID = 'ea1c4fd9-b0b9-4502-8fd8-417d3b537af9'
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
    }
    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:22.6.0-alpine'
                }
            }
            steps {
                sh '''
                   npm i netlify-cli
                   node_modules/.bin/netlify --version
                   node_modules/.bin/netlify status
                '''
            }
        }
    }
}