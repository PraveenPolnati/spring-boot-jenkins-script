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
                dir('path/to/your/subdirectory') {
                    sh 'mvn clean install'
                }
            }
        }
    }
}
