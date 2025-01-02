pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                // Cloning the repository from GitHub
                git 'https://github.com/PraveenPolnati/message.git'
            }
        }
        stage('Build Application') {
            steps {
                // Assuming it's a Maven project, you can use the following to build the app
                sh 'mvn clean install'
            }
        }
        stage('Run Application') {
            steps {
                // If it's a Spring Boot application, you can run it like this:
                sh 'java -jar target/message-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}
