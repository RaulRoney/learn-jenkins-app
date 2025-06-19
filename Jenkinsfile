pipeline {
    agent any

    stages {
        stage('sem docker') {
            steps {
                sh '''
                    echo 'sem docker'
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('docker') {
            agent {
                docker {
                    image 'node:18-alpine'S
                    reuseNode true
                }
            }
            steps {
               sh ' echo "docker" '
               sh 'npm --version'
               sh 'ls -la'
               sh 'touch container-yes.txt'
            }
        }
    }
}
