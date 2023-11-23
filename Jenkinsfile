pipeline {
    agent any
    environment {   
        GCLOUD_CREDENTIALS_FILE = './class-lab-3-e7bb5825c019.json'
        GCP_PROJECT = 'class-lab-3'
        VM_NAME = 'jenkin-1'
        VM_ZONE = 'us-central1-a'
        DEPLOYMENT_DIRECTORY = '/home/jayroy0054/jenkins/index.html'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'      
            } }
        stage('Test') {
            steps {
                echo 'Testing...'
            } }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                withCredentials([file(credentialsId: 'vm-ssh-key', variable: 'GCLOUD_CREDENTIALS_FILE')]) {
                    // Authenticate with GCP
                     sh 'gcloud auth activate-service-account --key-file=${GCLOUD_CREDENTIALS_FILE}'
                     sh 'gcloud config set project ${GCP_PROJECT}'
                    // Copy files to the Compute Engine instance
                     sh 'gcloud compute scp --zone=${VM_ZONE} ./index.html ${VM_NAME}:${DEPLOYMENT_DIRECTORY}'
                } } } }
    post {
        always {
            echo 'Cleaning up...'
            // Perform any cleanup tasks, like removing temporary files
            sh 'rm -rf target_directory/'   }}}
