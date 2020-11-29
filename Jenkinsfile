pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                timeout(time: 2, unit: 'MINUTES'){
                    retry(5){
                        sh "echo $PATH"
                    }
                }
            }   
        }
    }
    post('Post Result') {
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failure'
        }
    }
}
