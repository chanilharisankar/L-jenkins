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
                buildCode()
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

void buildCode() {
    echo 'push artifect to artifacts repository'
    echo 'this is artifect' >> artifacts.txt
}