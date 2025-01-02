pipeline {
    agent any

    tools {
        maven 'Maven-3.8.1'  // Maven installation in Jenkins (make sure the name matches what you configured)
        jdk 'JDK-11'         // JDK installation in Jenkins (make sure the name matches what you configured)
    }

    environment {
        JAR_NAME = 'greetings-0.0.1-SNAPSHOT.jar'  // Define your JAR name
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the correct Git branch from the repository
                git branch: 'master', url: 'https://github.com/PraveenPolnati/spring-boot-jenkins-script.git'
            }
        }

        stage('Build Application') {
            steps {
                // Build the project using Maven
                sh 'mvn clean install'  // This will run from the root of the repository
            }
        }

        stage('Run Application Locally') {
            steps {
                // Run the Spring Boot application locally using the JAR file
                sh 'java -jar target/${JAR_NAME}'  // Ensure the JAR is being created in the target folder
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
