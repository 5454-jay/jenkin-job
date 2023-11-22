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
                // Add steps if you need to build your project
                // For a simple HTML project, you may not need a build step
                echo 'Running build steps'
            }
        }

        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'class-lab-3', variable: 'GOOGLE_APPLICATION_CREDENTIALS')]) {
                    script {

                        sh "gcloud auth revoke --key-file=${GOOGLE_APPLICATION_CREDENTIALS}"
                        // Authenticate with GCP
                        sh "gcloud auth activate-service-account --key-file=${GOOGLE_APPLICATION_CREDENTIALS}"

                        // Copy files to Compute Engine instance
                        echo 'sh gcloud compute scp --recurse ./assets instance-name:/path/to/target-directory/assets --zone=your-instance-zone'
                        echo 'sh gcloud compute scp --recurse ./vendor instance-name:/path/to/target-directory/vendor --zone=your-instance-zone'
                        sh "gcloud compute scp ./index.html instance-name:jenkins/index.html --zone=us-central1-a"
                        echo 'files are copyed'
                        // Restart web server or perform any other necessary commands on the VM
                        // For example, if you're using Apache or Nginx, you might need to reload it
                        // sh "gcloud compute ssh instance-name --zone=your-instance-zone -- 'sudo systemctl reload apache2'"
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
