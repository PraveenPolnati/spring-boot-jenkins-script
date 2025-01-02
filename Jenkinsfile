pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build Application') {
            steps {
                dir('/welcome') {
                    sh 'mvn clean install'
                }
            }
        }
    }
}
