pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/VK18-Learn/Jenkins-demo.git'
            }
        }

        stage('Deploy to EC2') {
            steps {
                sh '''
                mkdir -p /home/ubuntu/jenkins-demo
                cp -r $WORKSPACE/* /home/ubuntu/jenkins-demo/
                pkill -f "python3 -m http.server" || true
                cd /home/ubuntu/jenkins-demo
                nohup python3 -m http.server 8000 > server.log 2>&1 &
                '''
            }
        }
    }
}
