pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/RahulRayaB-Dev/jenkins-pipeline-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 myapp:latest'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed successfully!'
        }
    }
}
