pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-demo"
    }

    stages {
        stage('Clone repository') {
            steps {
                git url: 'https://github.com/sl4yernic/jenkins-demo.git'
            }
        }

        stage('Build Docker image') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME}:latest ."
                }
            }
        }

        stage('Run basic test') {
            steps {
                echo 'Simulating test stage...'
                sh 'echo "Tests passed!"'
            }
        }

        stage('Cleanup message') {
            steps {
                echo "Build completed. You can run: docker run -p 3000:3000 ${IMAGE_NAME}"
            }
        }
    }
}

