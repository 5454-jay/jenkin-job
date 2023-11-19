pipeline {
    agent any
    stages {
        stage('Deploy to GCE') {
            steps {
                withCredentials([file(credentialsId: 'GCP_JSON_Key', variable: 'GCP_KEY')]) {
                    sh 'gcloud auth activate-service-account --key-file $GCP_KEY'
                    // Additional commands for deployment
                }
            }
        }
    }
}
