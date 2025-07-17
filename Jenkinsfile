pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("chandini2326/bio-harvesting")
                }
            }
        }

        stage('Stop Existing Container') {
            steps {
                sh '''
                    if [ $(docker ps -q --filter name=bioharvest-container) ]; then
                        docker stop bioharvest-container
                        docker rm bioharvest-container
                    fi
                '''
            }
        }

        stage('Run Docker Container on Port 8083') {
            steps {
                sh 'docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting'
            }
        }
    }
}

