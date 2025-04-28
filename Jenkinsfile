pipeline {
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
                echo 'Optional: Add HTML/CSS validation tools if needed'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Website is ready. You can manually deploy to server or hosting platform.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
