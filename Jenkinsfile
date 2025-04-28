pipeline {//Hi
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'No dependencies for HTML/CSS/JS'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step needed for plain HTML/CSS/JS'
            }
        }

        stage('Test') {
            steps {
                echo 'Optional: Add HTML/CSS/JS validation tools if needed'
            }
        }

        stage('Start Local Server') {
            steps {
                echo 'Starting local server...'
                sh """
                    start "" "C:/Program Files (x86)/Google/Chrome/Application/chrome.exe" http://localhost:8000
                """
            }
        }
    }

    post {
        success {
            echo 'Website deployed successfully on http://localhost:8000/'
        }
        failure {
            echo 'Deployment Failed.'
        }
    }
}
