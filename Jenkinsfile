pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using a shell script
                    sh 'g++ -o myProgram hello.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Print the output of the compiled .cpp file
                    sh './myProgram'
                }
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
            echo 'Pipeline failed'
        }
    }
}
