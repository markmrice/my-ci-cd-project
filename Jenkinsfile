node {
    stage('Checkout') {
        checkout scm
    }

    stage('Check Python Script') {
        sh 'ls -la'   // List files in the workspace
        sh 'cat app.py' // Print the contents of app.py
    }

    stage('Run Python Script') {
        sh '/usr/bin/python3 app.py'  // Explicit path to Python3
    }
}
