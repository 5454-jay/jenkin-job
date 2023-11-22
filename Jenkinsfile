pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: '6d19e24e-b65f-42f9-82db-0a8781083c95', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    // Your deployment scripts that require GCP authentication
                }
            }
        }
    }
}
