pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: '4b7a1aa7-631d-4a5c-851a-0cbb39665459', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    // Your deployment scripts that require GCP authentication
                }
            }
        }
    }
}
