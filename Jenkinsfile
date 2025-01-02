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
                sh 'mvn clean install'
            }
        }
    }
}
