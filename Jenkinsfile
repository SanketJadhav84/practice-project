pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }
        stage('Docker Build') {
            steps {
                sh "docker build -t practiceimg ."
            }
        }
        stage('Docker compose') {
            steps {
                sh "docker compose up -d"
            }
        }
    }
}
