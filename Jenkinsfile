pipeline {
    agent any

    environment {
        IMAGE_NAME = 'chandini2326/bio-harvesting'
        CONTAINER_NAME = 'bioharvest-container'
        PORT = '8083'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t chandini2326/bio-harvesting .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh '''
                    docker stop bioharvest-container || true
                    docker rm bioharvest-container || true
                '''
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 8083:80 --name bioharvest-container chandini2326/bio-harvesting'
            }
        }
    }

    post {
        success {
            echo "🚀 Website deployed at: http://localhost:8083"
        }
    }
}
