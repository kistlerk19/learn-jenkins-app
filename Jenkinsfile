pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without DOcker"
                    ls -la
                    touch continer-no.txt
                '''
            }
        }
        stage('w docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With Docker"
                    ls -la
                    touch continer-yes.txt
                '''
            }
        }
    }
}
