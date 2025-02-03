node {
    stage('Cleanup Workspace') {
        deleteDir()
    }

    stage('Checkout Code') {
        checkout scm
    }

    stage('Fix Permissions') {
        sh 'chown -R jenkins:jenkins .'  
        sh 'chmod +x app.py'  
    }

    stage('Verify Files Before Running Docker') {
        sh 'ls -la'  // List all files in the workspace
    }

    stage('Run Python in Docker') {
        sh '''
        WORKSPACE=$(pwd)
        echo "Running in workspace: $WORKSPACE"
        ls -la $WORKSPACE  # Ensure files exist before running Docker
        docker run --rm -v "$WORKSPACE:/app" -w /app python:3.9 python app.py
        '''
    }
}
