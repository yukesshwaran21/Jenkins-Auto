pipeline {
    agent {
        docker {
            image 'python:3.10'
        }
    }

    stages {
        stage('Install dependencies') {
            steps {
                sh '''
                    apt-get update && apt-get install -y python3-venv python3-pip
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    . venv/bin/activate
                    pytest test_app.py
                '''
            }
        }
    }
}
