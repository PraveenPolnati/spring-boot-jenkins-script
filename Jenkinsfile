pipeline {
    agent any

    tools {
        maven 'Maven-3.8.1'  // Maven installation in Jenkins (make sure Maven is installed on Jenkins)
        jdk 'JDK-11'         // JDK installation in Jenkins (make sure JDK is installed on Jenkins)
    }

    environment {
        // Set the name of the project directory and JAR file
        PROJECT_DIR = 'greetings'
        JAR_NAME = 'greetings-0.0.1-SNAPSHOT.jar'
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the Git repository
                git branch: 'main', url: 'https://github.com/PraveenPolnati/welcome.git'
            }
        }

        stage('Build Application') {
            steps {
                // Navigate to the project directory and build the project using Maven
                dir("${PROJECT_DIR}") {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Run Application Locally') {
            steps {
                // Run the Spring Boot application locally using the JAR file
                dir("${PROJECT_DIR}") {
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
