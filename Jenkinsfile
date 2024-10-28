pipeline {
    agent any
    environment {
        NPM_CONFIG_CACHE = "${env.WORKSPACE}/.npm-cache"
    }
    stages {
        stage('Build') {
            agent{
                 docker {
                    image 'node:18-alpine'
                    reuseNode true 
                }
            }
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
    }
}
