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
        stage('Deploy') {
            steps {
                script {
                    timeout(time: 10, unit: 'MINUTES') {
                    input(id: "Deploy", message: "Deploy ${params.project_name}?", ok: 'Deploy')
                }
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