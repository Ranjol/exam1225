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


    post {
        success {
            echo 'The pipeline completed successfully'
        }
        failure {
            echo 'The pipeline failed'
        }
    }
}
