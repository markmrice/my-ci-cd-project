node {
    stage('Fix Permissions') {
        sh 'chown -R jenkins:jenkins .'  // Ensure Jenkins user owns all files
        sh 'chmod +x app.py'  // Grant execution permissions
    }

    stage('Checkout') {
        checkout scm
    }
/*
    stage('Run Python Script') {
        sh '/usr/bin/python3 app.py'  // Explicit path to Python3
    }
*/
    stage('Run Python in Docker') {
        sh 'docker run --rm -v $(pwd):/app -w /app python:3.9 python3 app.py'
    }
}
