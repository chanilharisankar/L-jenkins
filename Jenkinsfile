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
                }
        }
        stage('Deploy test environment') {
            steps {
                echo 'deploying to test environment'
            }
        }
        stage('Functional test') {
            steps {
                echo 'Running Functional test'
            }
        }
    }
}