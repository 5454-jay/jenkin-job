pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'a12bc355-fca8-49b2-a46c-902ec8d9f8aa', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    // Your deployment scripts that require GCP authentication
                }
            }
        }
    }
}
