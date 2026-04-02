pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/VK18-Learn/Jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }
    }
}
