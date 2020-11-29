pipeline {
    agent any
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
            mail to: 'aderise2012@gmail.com',
                 subject: "Successful pipeline: ${currentBuild.fullDisplayName}",
                 body: "Some is right with: ${env.BUILD_URL} @here ${env.JOB_NAME} #${env.BUILD_NUMBER} has passed"
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failure'
        }
    }
}
