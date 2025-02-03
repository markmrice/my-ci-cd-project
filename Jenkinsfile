node {
    stage('Checkout') {
        checkout scm
    }

    stage('Verify Files in Workspace') {
        sh 'ls -la'  // List all files in the Jenkins workspace
    }

    stage('Run Python Script') {
        sh 'python3 app.py'  // Run Python script
    }
}
