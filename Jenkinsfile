pipeline {
    agent any
    stages {
        stage('Deploy to GCE') {
            steps {
                script {
                    // Set the path to your service account key
                    def serviceAccountKeyPath = 'steam-circlet-405222-f2cf4c5f26eb.json'
                    // Authenticate with GCP using the service account key
                    sh "gcloud auth activate-service-account --key-file=${serviceAccountKeyPath}"
                    
                    // Additional pipeline commands
                }
            }
        }
    }
}
