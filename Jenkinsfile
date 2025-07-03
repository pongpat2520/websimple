pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-web-cicd .'
            }
        }
        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f my-web || exit 0'
                bat 'docker run -d --name my-web -p 8080:80 my-web-cicd'
            }
        }
    }
}
