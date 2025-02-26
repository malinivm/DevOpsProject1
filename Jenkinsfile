pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/malinivm/DevOpsProject1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t app.py .'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker stop DevOpsProject1 || true'
                    sh 'docker rm DevOpsProject1 || true'
                    sh 'docker run -d --name DevOpsProject1 -p 5000:5000 app.py'
                }
            }
        }
    }
}
