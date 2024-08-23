pipeline {
    agent any
    stages {
        stage('Test Email') {
            steps {
                script {
                    emailext(
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Test Email from Jenkins',
                        body: 'This is a test email to verify the email configuration in Jenkins.',
                        attachLog: true
                    )
                }
            }
        }
    }
}
