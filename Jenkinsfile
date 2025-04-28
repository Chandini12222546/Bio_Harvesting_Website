pipeline { //hi
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Chandini12222546/Bio_Harvesting_Website.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'No dependencies for HTML/CSS'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step needed for plain HTML/CSS'
            }
        }

        stage('Test') {
            steps {
                echo 'Optional: Add HTML/CSS validation tools if needed'
            }
        }

        stage('Start Local Server') {
            steps {
                echo 'Starting local server...'
                sh """
                    cd Bio_Harvesting_Website
                    python3 -m http.server 8000
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
