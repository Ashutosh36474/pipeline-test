pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Ashutosh36474/pipeline-test.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    # Create virtual environment
                    python3 -m venv venv

                    # Activate venv
                    . venv/bin/activate

                    # Upgrade pip in venv
                    pip install --upgrade pip

                    # Install dependencies
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    # Activate venv
                    . venv/bin/activate

                    # Run tests
                    PYTHONPATH=. pytest
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
