pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
            post {
                always {
                    emailext (
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Jenkins Build Completed',
                        body: 'The build stage has completed.',
                        attachLog: true
                    )
                }
            }
        }
    }

    post {
        always {
            emailext (
                to: 'kirtikasharma5104@gmail.com',
                subject: 'Jenkins Pipeline Completed',
                body: 'The Jenkins pipeline has finished executing.',
                attachLog: true
            )
        }
    }
}
