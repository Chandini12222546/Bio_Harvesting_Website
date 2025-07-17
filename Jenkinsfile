pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("chandini2326/bio-harvesting")
                }
            }
        }

        stage('Stop & Remove Existing Container') {
            steps {
                sh '''
                    CONTAINER_ID=$(docker ps -aqf "name=bioharvest-container")
                    if [ ! -z "$CONTAINER_ID" ]; then
                        docker stop $CONTAINER_ID
                        docker rm $CONTAINER_ID
                    fi
                '''
            }
        }

        stage('Run Docker Container on Port 8083') {
            steps {
                sh '''
                    docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting
                '''
            }
        }
    }
}
