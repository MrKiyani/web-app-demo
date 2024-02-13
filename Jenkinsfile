pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning the repository...'
                git url: 'https://github.com/MrKiyani/web-app-demo.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the Docker image...'
                script {
                    // Build the Docker image
                    sh "docker build -t webapp-demo . -f Dockerfile"
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                script {
                    // Run the Docker container
                    sh "docker run -d -p 8090:8000 webapp-demo"
                }
            }
        }
    }
}
