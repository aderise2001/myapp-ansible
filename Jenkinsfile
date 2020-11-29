pipeline {
    agent {
        docker { image 'node:14-alpine' }
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
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failure'
        }
    }
}
