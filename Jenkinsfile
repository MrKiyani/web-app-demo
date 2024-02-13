pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/MrKiyani/web-app-demo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('adminturneddevops/go-webapp-sample')
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.image('adminturneddevops/go-webapp-sample').withRun('-p 8090:8000')
                }
            }
        }
    }
}
