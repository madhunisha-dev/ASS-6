pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Starting Build...'
                bat 'python -m py_compile app.py'
                echo 'Build successful: app.py compiled with no syntax errors'
            }
        }

        stage('Notification') {
            steps {
                echo 'Build completed successfully!'
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Build URL: ${env.BUILD_URL}"
            }
        }
    }
}