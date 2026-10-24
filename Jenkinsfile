pipeline {
    agent {
        node {
            label 'AGENT-1'
    
        }
    }
    environment {
        COURSE = "Jenkins"
    }
     options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 10, unit: 'SECONDS')
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                       echo "Building"
                       echo $COURSE
                       sleep 10
                       env
                    """
                 
                }    
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying"
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello!'
            cleanWs() 
        }
        success {
            echo 'I will run if success'
        }
        failure {
            echo 'I will run if failure'
        }
        aborted {
            echo 'Pipeline is aborted'
        }
    }
}

