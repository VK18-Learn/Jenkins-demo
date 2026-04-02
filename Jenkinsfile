pipeline {
    agent any

    stages {
        stage('Deploy to EC2') {
            steps {
                sshagent(['ec2-key']) {
                    sh '''
                    ssh -o StrictHostKeyChecking=no ubuntu@3.239.95.207"
                        cd /home/ubuntu &&
                        git pull &&
                        npm install &&
                        npm start
                    "
                    '''
                }
            }
        }
    }
}
