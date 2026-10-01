pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/madhunisha-dev/ASS-6.git'
            }
        }

        stage('Build') {
            steps {
                bat 'python -m py_compile app.py'
                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Send Notification') {
            steps {
                mail(
                    to: 'madhunishas2007@gmail.com',
                    cc: 'instructor@gmail.com',
                    subject: "Build Notification: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                    body: """The build for ${env.JOB_NAME} #${env.BUILD_NUMBER} has completed.

Check it here: ${env.BUILD_URL}"""
                )
            }
        }
    }
}