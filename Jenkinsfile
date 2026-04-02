pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sshagent(['your-credential-id']) {
                    bat '''
                    ssh -o StrictHostKeyChecking=no ubuntu@YOUR_EC2_IP "
                    echo 'Hello from Jenkins to AWS 🚀' > test.txt
                    "
                    '''
                }
            }
        }
    }
}
