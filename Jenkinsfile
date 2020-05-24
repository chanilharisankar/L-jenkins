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
    }
}