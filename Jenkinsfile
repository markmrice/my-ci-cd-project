node {
    stage('Cleanup Workspace') {
        deleteDir()  // Clears all files before checkout
    }

    stage('Checkout') {
        checkout scm
    }

    stage('Fix Permissions') {
        sh 'chown -R jenkins:jenkins .'  // Ensure Jenkins user owns all files
        sh 'chmod +x app.py'  // Grant execution permissions
    }
    
    stage('Run Python in Docker') {
        sh 'docker run --rm -v $(pwd):/app -w /app python:3.9 python3 app.py'
    }
}
