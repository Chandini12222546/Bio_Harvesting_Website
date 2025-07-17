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
                git 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME} ."
                }
            }
        }

        stage('Stop and Remove Existing Container') {
            steps {
                script {
                    def isRunning = sh(script: "docker ps -q -f name=${CONTAINER_NAME}", returnStdout: true).trim()
                    if (isRunning) {
                        sh "docker stop ${CONTAINER_NAME}"
                        sh "docker rm ${CONTAINER_NAME}"
                    }
                }
            }
        }

        stage('Run New Docker Container') {
            steps {
                script {
                    sh "docker run -d -p ${PORT}:80 --name ${CONTAINER_NAME} ${IMAGE_NAME}"
                }
            }
        }
    }

    post {
        success {
            echo "✅ Deployment successful! Visit: http://localhost:${PORT} or your Ngrok link"
        }
        failure {
            echo "❌ Deployment failed. Check console for errors."
        }
    }
}
