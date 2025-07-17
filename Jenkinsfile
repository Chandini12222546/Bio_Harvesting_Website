pipeline {
    agent any

    environment {
        IMAGE_NAME = 'chandini2326/bio-harvesting'
        CONTAINER_NAME = 'bioharvest-container'
        PORT = '8083'
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo '📥 Cloning GitHub repository...'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "🐳 Simulating Docker build: ${IMAGE_NAME}"
            }
        }

        stage('Stop and Remove Existing Container') {
            steps {
                echo "🛑 Simulating stop and remove of Docker container: ${CONTAINER_NAME}"
            }
        }

        stage('Run New Docker Container') {
            steps {
                echo "🚀 Simulating Docker run on port ${PORT} with image: ${IMAGE_NAME}"
            }
        }
    }

    post {
        success {
            echo "✅ Simulated deployment successful!"
            echo "🌐 Access would be at: http://localhost:${PORT} or Ngrok link"
        }
        failure {
            echo "❌ Simulated deployment failed. Please check the pipeline logs."
        }
    }
}
