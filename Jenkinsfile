pipeline jenkins{
    agent any{
        stages{
            stage('Build'){
                echo 'Building a pipeline'
                bat git branch: 'main', url: https://github.com/Ranjol/exam1225.git
            }
            stage('compile'){
                echo 'compiling the code'
                bat python app.py
            }
            stage('Test'){
                echo 'Testing the code'
                bat python app.py
            }
            stage ('Run'){
                echo 'running the code'
                bat python app.py
            }
        }
    }
}
post{
    success{
        echo 'the pipeline has been completed successfully'
    }
    failure{
        echo 'the pipeline has been failed'
    }
}