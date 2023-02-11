pipeline {
    agent any
    environment {
        name = 'techstart'
    }

    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal 2023
                '''
            }
        }
        stage('Environment Variable') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
            }
        }
        stage('Deploy the Package to test Env - continue?') {
            input {
                message "Should we continue or abort here"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy the Package to test Env'
                sh 'echo "${name}"'
            }
        }
        stage('Deploy the Package to Prod Env') {
            steps {
                echo 'Deploy the Package to Prod Env'
            }
        }
    }
     post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'failed'
        }
        success {
            echo 'success'
        }
    }
}
