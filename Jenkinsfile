pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
            post {
                success {
                    emailext(
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Build Success',
                        body: 'The build was successful.',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Build Failure',
                        body: 'The build failed. Please check the log for details.',
                        attachLog: true
                    )
                }
            }
        }
    }

    post {
        always {
            emailext(
                to: 'kirtikasharma5104@gmail.com',
                subject: 'Pipeline Complete',
                body: 'The Jenkins pipeline has finished executing.',
                attachLog: true
            )
        }
    }
}
