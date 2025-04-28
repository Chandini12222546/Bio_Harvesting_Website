pipeline { 
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Chandini12222546/Bio_Harvesting_Website.git'
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

        stage('Deploy') {
            steps {
                echo 'Website code cloned successfully.'
            }
        }
    }

    post {
        success {
            echo 'Website deployed successfully from GitHub!'
        }
        failure {
            echo 'Deployment Failed.'
        }
    }
}
