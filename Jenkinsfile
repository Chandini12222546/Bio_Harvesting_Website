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
                echo 'Deploying website...'

                 withCredentials([usernamePassword(credentialsId: 'ftp-credentials-id', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh """
                        lftp -c "open -u $USER,$PASS ftp://your-ftp-host.com && mirror -R ./ /public_html/"
                    """
                }

             }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed.'
        }
    }
}
