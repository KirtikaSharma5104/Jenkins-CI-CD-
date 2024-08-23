pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                echo 'Checking out the code from SCM...'
                // Example: If you're using Git
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/your-repo.git']]])
            }
        }

        stage('Build') {
            steps {
                echo 'Building the code...'
                // Example: If you're using Maven to build a Java project
                sh 'mvn clean install'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                // Example: Running tests using Maven
                sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis...'
                // Example: Running SonarQube analysis
                sh 'mvn sonar:sonar'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing Security Scan...'
                // Example: Running a security scan using a tool like OWASP Dependency Check
                sh 'mvn dependency-check:check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging Environment...'
                // Example: Deploying to staging using a script or a tool like Ansible
                sh './deploy.sh staging'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Example: Running integration tests against the staging environment
                sh './run-integration-tests.sh staging'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production Environment...'
                // Example: Deploying to production using a script or a tool like Ansible
                sh './deploy.sh production'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'kirtikasharma5104@gmail.com',
                subject: 'Pipeline Success',
                body: 'The Jenkins pipeline has successfully completed.',
                attachLog: true
            )
        }
        failure {
            emailext(
                to: 'kirtikasharma5104@gmail.com',
                subject: 'Pipeline Failed',
                body: 'The Jenkins pipeline has failed. Please check the logs for more details.',
                attachLog: true
            )
        }
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
