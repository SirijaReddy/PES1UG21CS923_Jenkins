pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                build 'PES1UG21CS923-1'
                sh 'g++ hello.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
            }
        }
        
        stage('Deploy') {
            steps {
                // Add deployment steps if needed
                echo 'Deployment steps go here'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
