pipeline {
    agent any
    stages {
        stage('Checkout') {////
            steps {
                git branch: 'main', url: 'https://github.com/yukesshwaran21/Jenkins-Auto.git'
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                    pip install --user pytest
                    export PATH=$PATH:$HOME/.local/bin
                    pytest
                '''
            }
        }
    }
    post {
        always {//
            echo 'Cleaning up.....'//
        }
        success {
            echo 'Tests passed successfully!'
        }
        failure {
            echo 'Tests failed. Please check logs.'
        }
    }
}

