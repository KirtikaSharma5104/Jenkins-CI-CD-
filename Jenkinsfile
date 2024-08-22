pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                script {
                    echo 'Build automation tool: Maven'
                    // Example: sh 'mvn clean install'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                script {
                    echo 'Test automation tool: JUnit for unit tests, Selenium for integration tests'
                    // Example: sh 'mvn test'
                }
            }
            post {
                always {
                    emailext subject: "Unit and Integration Tests Completed",
                            body: "The unit and integration tests stage has completed successfully.",
                            to: "kirtikasharma5104@gmail.com",
                            attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                script {
                    echo 'Code analysis tool: SonarQube'
                    // Example: sh 'mvn sonar:sonar'
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                script {
                    echo 'Security scan tool: OWASP Dependency-Check'
                    // Example: sh 'dependency-check.sh --project myapp --scan .'
                }
            }
            post {
                always {
                    emailext subject: "Security Scan Completed",
                            body: "The security scan stage has completed successfully.",
                            to: "kirtikasharma5104@gmail.com",
                            attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                script {
                    echo 'Deployment target: AWS EC2 instance (staging)'
                    // Example: sh 'deploy-to-ec2.sh --environment staging'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                script {
                    echo 'Integration tests tool: Selenium'
                    // Example: sh 'run-selenium-tests.sh'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                script {
                    echo 'Deployment target: AWS EC2 instance (production)'
                    // Example: sh 'deploy-to-ec2.sh --environment production'
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
