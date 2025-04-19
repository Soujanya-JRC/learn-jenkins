pipeline {
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 2, unit: 'MINUTES')
        disableConcurrentBuilds()
        //retry(1)
    }
    parameters {
        string(name: 'PPERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                 sh "echo this is build"
                 //sh 'sleep 30'
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
    
        stage('print params'){
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }
    post {
        always{
            echo "this section run always"
            deleteDir()
        }
        success{
            echo "this section run when pipeline success"
        }
        failure{
            echo "this section run when pipeline fails"
        }
    }

}