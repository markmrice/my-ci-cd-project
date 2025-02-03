node {
    stage('Cleanup Workspace') {
        deleteDir()  // Clears old files
    }

    stage('Checkout Code') {
        checkout scm  // Clone the repo
    }

    stage('Fix Permissions') {
        sh 'chown -R jenkins:jenkins .'  
        sh 'chmod +x app.py'  
    }

    stage('Run Python in Docker') {
        sh 'docker run --rm -v "$(pwd)":/app -w /app python:3.9 python3 app.py'
    }
}
