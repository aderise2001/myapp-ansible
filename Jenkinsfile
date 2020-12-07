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
           emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
                    to: "${EMAIL_TO}", 
                    subject: 'Build failed in Jenkins: $PROJECT_NAME - #$BUILD_NUMBER'
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failure'
        }
    }
}

