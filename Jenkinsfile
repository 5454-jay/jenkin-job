pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: '4bc22f5b-01ba-4cb7-883d-e7088d8a4aae', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    // Your deployment scripts that require GCP authentication
                }
            }
        }
    }
}
