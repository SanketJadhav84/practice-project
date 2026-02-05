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
        stage('Webhook Verification') {
            steps {
                sh '''
                    echo "=== WEBHOOK CHECK ==="
                    echo "BUILD NUMBER: $BUILD_NUMBER"
                    echo "GIT COMMIT:"
                    git rev-parse HEAD
                    echo "GIT BRANCH:"
                    git branch --show-current
                    echo "====================="
                    '''
            }
        }

    }
}
