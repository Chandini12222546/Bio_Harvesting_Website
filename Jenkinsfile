pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Checkout your GitHub repo
                git 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image with tag
                    docker.build('chandini2326/bio-harvesting')
                }
            }
        }

        stage('Stop & Remove Existing Container') {
            steps {
                // Stop and remove the container if it exists
                sh '''
                    if [ $(docker ps -q -f name=bioharvest-container) ]; then
                        docker stop bioharvest-container
                        docker rm bioharvest-container
                    fi
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                // Run the container on port 8083 mapped to container's port 80
                sh 'docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting'
            }
        }
    }
}
