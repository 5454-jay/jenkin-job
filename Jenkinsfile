pipeline {
    agent any
    stages {
        stage('Deploy to GCE') {
            steps {
                
                withCredentials([file(credentialsId: 'a12bc355-fca8-49b2-a46c-902ec8d9f8aa', variable: 'GCP_KEY')]) {
    sh 'gcloud auth activate-service-account --key-file $GCP_KEY'
    // Additional pipeline commands
}


            }
        }
    }
}
