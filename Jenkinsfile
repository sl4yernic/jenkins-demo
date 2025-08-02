pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-demo-app"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/sl4yer/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building Docker image..."
                sh "docker build -t $IMAGE_NAME:latest ."
            }
        }

        stage('Test') {
            steps {
                echo "Running dummy tests..."
                sh "echo OK"
            }
        }

        stage('Cleanup') {
            steps {
                echo "Done. You can now run: docker run -p 3000:3000 $IMAGE_NAME"
            }
        }
    }
}

