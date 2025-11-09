pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sagarkasapu2003/python-ci-pipeline-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                    echo "Building Docker image..."
                    docker build -t python-ci-demo:latest .
                    docker images | grep python-ci-demo
                '''
            }
        }

        stage('Verify Docker Image') {
            steps {
                sh '''
                    echo "Verifying image build..."
                    docker images | grep python-ci-demo && echo "✅ Docker image exists!"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "🚀 Docker image build verified successfully!"
            }
        }
    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed!"
        }
    }
}
