pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/madhunisha-dev/ASS-6.git'
            }
        }

        stage('Build') {
            steps {
                bat 'C:\\Users\\madhu\\AppData\\Local\\Programs\\Python\\Python312\\python.exe py_compile app.py'
                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Send Notification') {
            steps {
                mail to: 'student@example.com',
                     cc: 'instructor@example.com',
                     subject: "Build Notification: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                     body: "The build for ${env.JOB_NAME} has completed.\n\nCheck it here: ${env.BUILD_URL}"
            }
        }
    }
}