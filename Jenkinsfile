pipeline {
    agent any
    environment {
        EMAIL_TO = 'aderise2012@gmail.com'
    }
    stages {
        stage('build') {
            steps {
                timeout(time: 2, unit: 'MINUTES'){
                    retry(5){
                        sh 'echo $USER'
                        sh 'node --version'
                    }
                }
            }   
        }
    }
    post('Post Result') {
        success {
            echo 'Message: Started: Job - ${env.JOB_NAME} ${env.BUILD_NAME} ${env.BUILD_URL}
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failure'
        }
    }
}

