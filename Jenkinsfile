node {
    stage('Checkout') {
        checkout scm
    }

    stage('Check Python Script') {
        sh 'ls -la'   // List files in the workspace
        sh 'cat app.py' // Print the contents of app.py
    }

    stage('Verify Working Directory') {
        sh 'pwd'  // Print the current directory
        sh 'ls -la'  // Show workspace files
    }

    stage('Run Python Script') {
        sh '/usr/bin/python3 app.py'  // Explicit path to Python3
    }
}
