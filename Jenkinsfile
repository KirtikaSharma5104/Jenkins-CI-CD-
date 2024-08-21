pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    
    post {
        success {
            mail to: 'kirtikasharma5104@gmail.com',
                 subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Good news! Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded."
        }
        failure {
            mail to: 'kirtikasharma5104@gmail.com',
                 subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Unfortunately, Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed."
        }
    }
}
