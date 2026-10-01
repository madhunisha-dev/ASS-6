pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Starting Checkout...'
                git branch: 'main',
                    url: 'https://github.com/madhunisha-dev/ASS-6.git'
                echo 'Checkout completed successfully!'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting Build...'
                bat 'python -m py_compile app.py'
                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Send Notification') {
            steps {
                echo 'Sending build notification...'

                mail to: 'student@example.com',
                     subject: "Build Notification: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The build for ${env.JOB_NAME} has completed.\n\nCheck it here: ${env.BUILD_URL}"

                echo 'Notification stage completed!'
            }
        }
    }
}