pipeline {
    agent any

    tools {
        maven 'Maven-3.8.1'  // Ensure this matches the installed Maven tool in Jenkins
        jdk 'JDK-11'         // Ensure this matches the installed JDK in Jenkins
    }

    environment {
        JAR_NAME = 'welcome-0.0.1-SNAPSHOT.jar'  // The name of the JAR file (you can change this if needed)
    }

    stages {
        stage('Checkout SCM') {
            steps {
                // Clone the repository from the new GitHub URL
                git branch: 'master', url: 'https://github.com/PraveenPolnati/welcome.git'
            }
        }

        stage('Build Application') {
            steps {
                // Navigate to the directory containing the pom.xml (if needed)
                dir('welcome') {
                    // Run the Maven build command
                    sh 'mvn clean install'
                }
            }
        }

        stage('Run Application Locally') {
            steps {
                // Navigate to the 'welcome' directory to run the application
                dir('welcome') {
                    // Run the Spring Boot application locally (from the target folder)
                    sh 'java -jar target/${JAR_NAME}'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and application started successfully.'
        }
        failure {
            echo 'Build or application startup failed.'
        }
    }
}
