pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image from the root directory (make sure Dockerfile exists)
                    def customImage = docker.build("chandini2326/bio-harvesting")
                }
            }
        }

        stage('Stop & Remove Existing Container') {
            steps {
                script {
                    // Safely stop and remove container if it exists
                    def containerId = sh(script: "docker ps -q --filter name=bioharvest-container", returnStdout: true).trim()
                    if (containerId) {
                        sh "docker stop bioharvest-container"
                        sh "docker rm bioharvest-container"
                    } else {
                        echo "No container named bioharvest-container running"
                    }
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting'
            }
        }
    }
}
