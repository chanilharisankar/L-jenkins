pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world! Stage 1' 
            }
        }
        stage('Stage 2') {
            steps {
                parallel(
                    a: { echo "Stage 2 This is branch a" },
                    b: { echo "Stage 2 This is branch b" }
                    )
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Hello world! Stage 3' 
            }
        }
    }
}