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
                sh 'bash build.sh'
                archiveArtifacts artifacts: 'artifect.txt'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    timeout(time: 1, unit: 'MINUTES') {
                    input(id: "Deploy", message: "Deploy ${params.project_name}?", ok: 'Deploy')
                    echo 'yooo deploying'
                }
            }
            }
        }
        stage('read archive') {
            steps {
                copyArtifacts filter: 'artifect.txt', projectName: '${JOB_NAME}'
                sh 'cat artifect.txt'
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