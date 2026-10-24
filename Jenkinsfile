pipeline {
    agent {
        node {
            label 'AGENT-1'
    
        }
    }
    environment {
        COURSE = "Jenkins"
    }
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                       echo "Building"
                       echo $COURSE
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
    }
}

