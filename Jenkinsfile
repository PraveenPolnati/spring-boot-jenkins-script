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
                script {
                    // Ensure Maven is installed and available in your environment
                    sh 'mvn clean install'  // Run Maven from the root where pom.xml is located
                }
            }
        }
        
        stage('Run Application Locally') {
            steps {
                echo 'Run Application Locally'  // Placeholder for local application startup
            }
        }
    }
    post {
        always {
            echo 'Build or application startup finished.'
        }
    }
}
