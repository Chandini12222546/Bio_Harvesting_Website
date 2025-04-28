pipeline { //Hi
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Pull code from your source control (GitHub, GitLab, etc.)
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

                // Example: deploying via FTP (requires credentials setup in Jenkins)
                withCredentials([usernamePassword(credentialsId: 'ftp-credentials-id', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    sh """
                        lftp -c "open -u $USER,$PASS ftp://your-ftp-host.com && mirror -R ./ /public_html/"
                    """
                }

                // For GitHub Pages or Netlify, you can push changes or run a deploy script instead.
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
