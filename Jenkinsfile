pipeline {
    agent {
        label 'AGENT-1'
    }
    stages {
        stage('Build') {
            steps {
                 sh "echo this is build"
            }
        }
        stage('Test') {
            steps {
                sh "echo this is test"
                
            }
        }
        stage('Deploy') {
            steps {
                sh "echo this is deploy"
            }
        }
    }


    post {
        always{
            echo "this section run always"
        }
        success{
            echo "this section run when pipeline success"
        }
        failure{
            echo "this section run when pipeline fails"
        }
    }

}