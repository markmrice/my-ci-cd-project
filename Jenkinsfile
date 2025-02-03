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

    stage('Run Python in Docker') {
        sh '''
        WORKSPACE="$(pwd)"
        docker run --rm -v "${WORKSPACE}:/app" -w /app python:3.9 python3 app.py
        '''
    }
}
