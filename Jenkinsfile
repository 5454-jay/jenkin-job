pipeline {
    agent any
    stages {
        // ... other stages like Checkout, Build

        stage('Deploy') {
            steps {
                withCredentials([file(credentialsId: 'vm-ssh-key', variable: 'SECRET_FILE')]) {
                    // Use the secret file for deployment
                    // For example, if it's an SSH key for SCP
                    echo 'sh scp -i ${SECRET_FILE} ./index1.html jayroy0054@134.132.205.223:/home/jayroy0054/jenkins/'
                    sh "scp -i ${SECRET_FILE} -o StrictHostKeyChecking=no ./index1.html jayroy0054@134.132.205.223:/home/jayroy0054/jenkins/"

                    // Additional deployment steps
                }
            }
        }
    }
    // ... post-stages
}
