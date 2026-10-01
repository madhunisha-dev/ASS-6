pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo '===== BUILD STARTED ====='

                bat 'python --version'

                bat 'python -m py_compile app.py'

                echo '===== BUILD SUCCESSFUL ====='
                echo 'app.py compiled successfully'
            }
        }

        stage('Notification') {
            steps {
                echo '===== BUILD COMPLETED ====='
                echo "Job Name: ${env.JOB_NAME}"
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Build URL: ${env.BUILD_URL}"
            }
        }
    }
}