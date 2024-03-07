pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/SirijaReddy/PES1UG21CS923_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                // Adjust this part based on your project structure
                script {
                    build 'PES1UG21CS923-1'
                    sh 'g++ hello2.cpp -o output'
                    // Add any other build commands if needed
                }
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
                // Add deployment steps if needed
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
