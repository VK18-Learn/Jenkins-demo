pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/VK18-Learn/Jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'scp target/app.jar ubuntu@<EC2-IP>:/home/ubuntu/'
                sh 'ssh ubuntu@<EC2-IP> "nohup java -jar /home/ubuntu/app.jar &"'
            }
        }
    }
}
