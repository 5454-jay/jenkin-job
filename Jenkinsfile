pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
        stage('Deploy to GCE') {
    steps {
        withCredentials([file(credentialsId: 'b7707729-bcd5-448d-b326-d4df79ad4955', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
            sh 'gcloud auth activate-service-account --key-file $GOOGLE_APPLICATION_CREDENTIALS'
            sh 'gcloud config set project steam-circlet-405222'
            // Your gcloud commands for deployment
            sh 'gcloud compute instances update-container jenkins'
        }
    }
}

    }
}
