stage('Deploy to EC2') {
    steps {
        sh '''
        # Copy all repo files to deployment folder
        cp -r $WORKSPACE/* /home/ubuntu/jenkins-demo/
        
        # Optional: start a local server to test
        # Kill any existing server first
        pkill -f "python3 -m http.server 8000" || true
        cd /home/ubuntu/jenkins-demo
        nohup python3 -m http.server 8000 > server.log 2>&1 &
        '''
    }
}
