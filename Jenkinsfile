node {
    stage('Checkout') {
        checkout scm
    }

    stage('Run Python Script') {
        sh '/usr/bin/python3 app.py'  // Explicit path to Python3
    }
}
