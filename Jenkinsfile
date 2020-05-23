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
                dir('apitests') {
                    git url: 'https://github.com/chanilharisankar/bootcamp-automation.git'
                }
                sh 'bash run-here/run-api-test.sh'
                }
        }
        stage('UI test') {
            steps {
                echo 'Running UI tests in docker'
                dir('uitests') {
                    git url: 'https://github.com/chanilharisankar/bootcamp-automation.git'
                }
                sh 'bash run-here/run-ui-test.sh'
                }
        }
        
    }
}