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
            }
        }
        stage('Deploy') {
            steps {
                script {
                    timeout(time: 1, unit: 'MINUTES') {
                    input(id: "Deploy", message: "Deploy ${params.project_name}?", ok: 'Deploy')
                    echo 'yooo deploying'
                    cat artifect.txt
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
    // post {
    //     always {
    //         archiveArtifacts artifacts: 'artifect.txt', onlyIfSuccessful: true
    //     }
    // }
}