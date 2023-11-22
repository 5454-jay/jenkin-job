pipeline {
    agent any

    environment {
        GOOGLE_APPLICATION_CREDENTIALS = 'gcpkey3.json'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout from Git repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Simpler build step, just creating a hello world text
                sh 'echo "Hello World" > hello.txt'
                echo 'Running build steps'
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'class-lab-3', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    script {
                        // Authenticate with GCP
                        sh "gcloud auth activate-service-account --key-file=${GOOGLE_APPLICATION_CREDENTIALS}"

                        // Copy the hello.txt file to Compute Engine instance
                        sh "gcloud compute scp ./readme.txt instance-name:jenkin/readme.txt --zone=us-central1-a"
                        echo 'Hello World text file is copied'

                        // If needed, execute additional commands on the VM
                        // Example: Run a command on the VM to display the content of hello.txt
                        // sh "gcloud compute ssh instance-name --zone=us-central1-a -- 'cat jenkins/hello.txt'"
                    }
                }
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up'
            // Perform any cleanup tasks
        }
    }
}
