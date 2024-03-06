pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
                echo 'uild stage successful'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
                echo 'Test stage successful'
                post {
                    always {
                        junit 'target/surefire-reports/*.xml'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                sh 'mvn deploy'
                echo 'Deployment successful'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
