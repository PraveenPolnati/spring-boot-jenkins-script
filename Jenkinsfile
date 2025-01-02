pipeline {
    agent any 
    stages {
        stage('Install JDK') {
            steps {
                // Use the 'tool' step to access a pre-configured JDK in Jenkins Global Tool Configuration
                withEnv(tool: 'jdk-22') { 
                    sh 'echo $JAVA_HOME' // Verify installation path
                }
            }
        }
    }
}