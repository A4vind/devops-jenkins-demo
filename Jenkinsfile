pipeline {
    agent any

    environment {
        PATH = "C:\Users\HP\AppData\Local\Programs\DockerDesktop\resources\bin\docker;${env.PATH}"
    }

    stages {
        stage('build image') {
            steps {
                echo 'Building the Docker image...'
                bat 'docker build -t devops-jenkins-demo-image .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Starting the container...'
                bat 'docker rm -f devops-jenkins-demo-container || exit 0'
                bat 'docker run -d --name devops-jenkins-demo-container -p 8081:80 devops-jenkins-demo-image'
            }
        }
    }
}
