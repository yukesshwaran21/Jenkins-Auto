pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yukesshwaran21/Jenkins-Auto.git'  // Replace with your repository
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    // Install dependencies (if any)
                    sh 'pip install -r requirements.txt' // Use pip for Python dependencies

                    // Run the tests
                    sh 'pytest'  // If using pytest for testing Python code
                }
            }
        }
    }
    post {
        always {
            // Clean up or notifications can go here if needed
            echo 'Cleaning up...'
        }
        success {
            echo 'Tests passed successfully!'
        }
        failure {
            echo 'Tests failed. Please check logs.'
        }
    }
}
