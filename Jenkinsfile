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
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'yooo deploying'
                }
            }
            }
        stage('API test') {
            steps {
                echo 'Running API tests in docker'
                dir('api-tests') {
                    git url: 'https://gitlab.com/saurav.gupta/basic-rest-assured.git'
                }
                sh 'cd api-tests && mvn clean test -DsuiteXmlFile=testng.xml'
                }
        }
        stage('UI test') {
            steps {
                echo 'Running UI tests in docker'
                dir('ui-tests') {
                    git url: 'https://github.com/chanilharisankar/bootcamp-automation.git'
                }
                sh 'bash run-here/run-ui-test.sh'
                }
        }
    }
}