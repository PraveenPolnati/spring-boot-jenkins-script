pipeline {
    agent any

    environment {
        // Define the directory where you want to clone your repository
        // REPO_DIR = 'workspace/spring-boot-app'
    }

    stages {
        stage('Checkout SCM') {
            steps {
                // Clone the repository into the specified directory
                dir(REPO_DIR) {
                    git 'https://github.com/PraveenPolnati/message'
                }
            }
        }

        // stage('Build Application') {
        //     steps {
        //         // Navigate to the cloned directory and run the Maven build
        //         dir(REPO_DIR) {
        //             sh 'mvn clean install'
        //         }
        //     }
        // }

        // stage('Run Spring Boot Application') {
        //     steps {
        //         // Run the Spring Boot application from the cloned directory
        //         dir(REPO_DIR) {
        //             sh 'java -jar target/*.jar'
        //         }
        //     }
        // }
    }
}
