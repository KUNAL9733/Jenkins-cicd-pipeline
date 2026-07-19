pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo:v1 .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f jenkins-web || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name jenkins-web -p 8085:80 jenkins-demo:v1'
            }
        }

    }
}
