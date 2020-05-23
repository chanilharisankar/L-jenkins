pipeline {
    agent any 
    stages {
        stage('Unit test') {
            steps {
                echo 'Running unit tests'
                echo 'Running Contract tests'
            }
        }
        stage('Build') {
            steps {
                echo 'building...'
                echo 'push artifect to artifacts repository'
            }
        }
        stage('Api test') {
            steps {
                echo 'Running API tests in docker'
                dir('run-here') {
                    git url: 'https://github.com/chanilharisankar/bootcamp-automation.git'
                }
                sh 'bash run-here/run-api-test.sh'
                }
        }
        
    }
}