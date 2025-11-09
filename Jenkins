pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sagarkasapu2003/python-ci-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                    echo "Installing dependencies..."
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Application') {
            steps {
                sh '''
                    echo "Running Python script..."
                    python3 app.py
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "🚀 Deploying app (placeholder — add Docker or SCP later)"
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
