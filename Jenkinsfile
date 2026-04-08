pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/kunal22823/NodeHtmlDocker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-node-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker stop my-container || exit 0'
                bat 'docker rm my-container || exit 0'
                bat 'docker run -d -p 8070:3000 --name my-container my-node-app'
            }
        }
    }
}
