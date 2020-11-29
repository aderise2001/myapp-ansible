pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                docker image 'maven:3.3.3'
                sh 'mvn --version'
            }
        }
    }
}
