pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                script {
                    echo 'Build automation tool: Maven'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                script {
                    echo 'Test automation tools: JUnit for unit tests, Selenium for integration tests'
                }
            }
            post {
                always {
                    emailext(
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Unit and Integration Tests Completed',
                        body: 'The unit and integration tests stage has completed.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                script {
                    echo 'Code analysis tool: SonarQube'
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                script {
                    echo 'Security scan tool: OWASP Dependency-Check'
                }
            }
            post {
                always {
                    emailext(
                        to: 'kirtikasharma5104@gmail.com',
                        subject: 'Security Scan Completed',
                        body: 'The security scan stage has completed.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                script {
                    echo 'Deployment target: AWS EC2 instance (staging)'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                script {
                    echo 'Integration tests tool: Selenium'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                script {
                    echo 'Deployment target: AWS EC2 instance (production)'
                }
            }
        }
    }

    post {
        always {
            emailext(
                to: 'kirtikasharma5104@gmail.com',
                subject: 'Jenkins Pipeline Completed',
                body: 'The Jenkins pipeline has finished executing.',
                attachLog: true
            )
        }
    }
}
