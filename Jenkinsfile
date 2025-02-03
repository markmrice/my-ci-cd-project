node {
    stage('Checkout') {
        checkout scm  // Ensures the latest code is pulled
    }

    stage('Python') {
        sh 'python3 app.py'  // Use python3 to ensure it's available
    }
}
