pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Checking out the source code'
                git branch: 'main', url: 'https://github.com/Ranjol/exam1225.git'
            }
        }

        stage('Compile') {
            steps {
                echo 'Checking Python syntax'
                bat 'python -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Flask route smoke tests'
                bat '''
python -c "from app import app; client = app.test_client(); assert client.get('/').status_code == 200; assert client.post('/register', data={'name': 'Test', 'email': 'test@example.com', 'password': 'secret', 'event': 'Demo'}).status_code == 200"
'''
            }
        }
    }

    post {
        success {
            echo 'The pipeline completed successfully'
        }
        failure {
            echo 'The pipeline failed'
        }
    }
}
