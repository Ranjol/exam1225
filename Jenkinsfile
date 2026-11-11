pipeline {
    agent any

    environment {
        PYTHON = 'py -3'
    }

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
                bat '%PYTHON% -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Flask route smoke tests'
                bat '%PYTHON% app.py'
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
