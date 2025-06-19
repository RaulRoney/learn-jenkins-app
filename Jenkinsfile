pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
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
            s
        }
        stage('Test') {
            steps{
                sh  '''
                    grep 'index.html' learn-jenkins-app/learn-jenkins-app/build
                    npm test -a
                '''
            }

        }
    }
}
