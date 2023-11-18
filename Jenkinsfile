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
        withCredentials([[$class: 'FileBinding', credentialsId: 'b7707729-bcd5-448d-b326-d4df79ad4955', variable: 'GOOGLE_APPLICATION_CREDENTIALS']]) {
            sh 'gcloud auth activate-service-account --key-file $GOOGLE_APPLICATION_CREDENTIALS'
            sh 'gcloud config set project steam-circlet-405222'
            // Deploying a Docker image to GCE
            sh 'gcloud compute instances update-container jenkins --container-image gcr.io/steam-circlet-405222/hie:tag'
        }
    }
}


    }
}
