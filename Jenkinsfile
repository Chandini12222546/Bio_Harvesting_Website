pipeline {
    agent any

    options {
        // Keep this build forever
        keepBuilds(1)
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the repository...'
                git 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    echo 'Building Docker image chandini2326/bio-harvesting...'
                    def customImage = docker.build("chandini2326/bio-harvesting")
                }
            }
        }

        stage('Stop & Remove Existing Container') {
            steps {
                echo 'Stopping and removing existing Docker container if any...'
                sh '''
                    if [ $(docker ps -q --filter name=bioharvest-container) ]; then
                        docker stop bioharvest-container
                        docker rm bioharvest-container
                    fi
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running Docker container...'
                sh 'docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting'
            }
        }
    }
}
