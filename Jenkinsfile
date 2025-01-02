pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                // Clone the repository
                script {
                    // Specify the directory to clone the repository into
                    def repoDir = 'newone'

                    // Clone the repository into the specified directory
                    git branch: 'main', url: 'https://github.com/PraveenPolnati/spring-boot-jenkins-script.git', dir: repoDir
                }
            }
        }
    }
}
