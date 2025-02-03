node {
    stage('Cleanup Workspace') {
        deleteDir()
    }

    stage('Verify Files Before Running Docker') {
        sh 'ls -la'  // List all files in the workspace
    }

    stage('Checkout Code') {
        checkout scm
    }

    stage('Fix Permissions') {
        sh 'chown -R jenkins:jenkins .'  
        sh 'chmod +x app.py'  
    }

    stage('Grant Jenkins Access to Docker') {
        sh '''
        usermod -aG docker jenkins
        newgrp docker
        '''
    }



    stage('Run Python in Docker') {
        sh '''
        echo "Now running Python..."
        docker run --rm -v /var/jenkins_home/workspace/cloud_test:/app -w /app python:3.9 python3 app.py
        '''
    }
}
