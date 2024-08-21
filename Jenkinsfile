pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the code using Maven...'
                    // Specify the build automation tool
                    echo 'Tool: Maven'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests...'
                    // Specify the test automation tools
                    echo 'Tools: JUnit for unit tests, Selenium for integration tests'
                }
            }
            post {
                always {
                    mail to: 'kirtikasharma5104@gmail.com',
                         subject: "Jenkins: Unit and Integration Tests Stage Completed",
                         body: "Unit and Integration Tests have completed. Status: ${currentBuild.currentResult}\n\nLogs:\n${currentBuild.rawBuild.log}"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code quality...'
                    // Specify the code analysis tool
                    echo 'Tool: SonarQube'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan...'
                    // Specify the security scanning tool
                    echo 'Tool: OWASP ZAP'
                }
            }
            post {
                always {
                    mail to: 'kirtikasharma5104@gmail.com',
                         subject: "Jenkins: Security Scan Stage Completed",
                         body: "Security Scan has completed. Status: ${currentBuild.currentResult}\n\nLogs:\n${currentBuild.rawBuild.log}"
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to staging server...'
                    // Specify the deployment tool or environment
                    echo 'Environment: AWS EC2'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging...'
                    // Specify the testing environment
                    echo 'Tools: JUnit, Selenium'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server...'
                    // Specify the production environment
                    echo 'Environment: AWS EC2'
                }
            }
        }
    }

    post {
        success {
            mail to: 'kirtikasharma5104@gmail.com',
                 subject: "Jenkins Pipeline Success",
                 body: "The Jenkins pipeline has completed successfully."
        }
        failure {
            mail to: 'kirtikasharma5104@gmail.com',
                 subject: "Jenkins Pipeline Failed",
                 body: "The Jenkins pipeline has failed. Check the Jenkins logs for more details.\n\nLogs:\n${currentBuild.rawBuild.log}"
        }
    }
}
