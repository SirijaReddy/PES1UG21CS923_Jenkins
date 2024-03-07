pipeline {
    agent any
    
    stages {
        stage('Clone Repository'){
            steps{
                checkout([
                    $class: 'GitSCM',
                    branches:[[naame: "*/main"]],
                    userRemoteConfigs:[[url: 'https://github.com/SirijaReddy/PES1UG21CS923_Jenkins.git']]
                    
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS923-1'
                sh 'g++ hello2.cpp -o output'
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
