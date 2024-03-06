pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                // Cloning the repository using Git
                git branch: 'main',
                url: 'https://github.com/VismayRBGowda/PES1UG21CS720_Jenkins.git'
            }
        }
        
        stage('Build') {
            steps {
                // Compiling the C++ file using g++
                sh 'g++ main/hello.cpp -o main/hello_exec'
            }
        }
        
        stage('Test') {
            steps {
                // Running the compiled C++ program
                sh './main/hello_exec'
            }
        }
    }
    
    post {
        always {
            // Post-action to execute regardless of the pipeline result
            echo 'Pipeline execution completed.'
        }
        
        success {
            // Post-action to execute if the pipeline is successful
            echo 'Pipeline succeeded.'
        }
        
        failure {
            // Post-action to execute if the pipeline fails
            echo 'Pipeline failed.'
        }
    }
}
