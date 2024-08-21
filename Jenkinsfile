pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Simulate a build process, e.g., using Maven
                script {
                    echo 'Build automation tool: Maven'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Simulate running tests
                script {
                    echo 'Test automation tool: JUnit for unit tests, Selenium for integration tests'
                }
            }
            post {
                always {
                    // Send email notification after tests
                    emailext subject: "Unit and Integration Tests Completed",
                            body: "The unit and integration tests stage has completed.",
                            to: "kirtikasharma5104@gmail.com",
                            attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Simulate code analysis
                script {
                    echo 'Code analysis tool: SonarQube'
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Simulate a security scan
                script {
                    echo 'Security scan tool: OWASP Dependency-Check'
                }
            }
            post {
                always {
                    // Send email notification after security scan
                    emailext subject: "Security Scan Completed",
                            body: "The security scan stage has completed.",
                            to: "kirtikasharma5104@gmail.com",
                            attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Simulate deployment to staging
                script {
                    echo 'Deployment target: AWS EC2 instance (staging)'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Simulate running integration tests on staging
                script {
                    echo 'Integration tests tool: Selenium'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Simulate deployment to production
                script {
                    echo 'Deployment target: AWS EC2 instance (production)'
                }
            }
        }
    }

    post {
        always {
            emailext subject: "Jenkins Pipeline Completed",
                    body: "The Jenkins pipeline has finished executing.",
                    to: "kirtikasharma5104@gmail.com",
                    attachLog: true
        }
    }
}
