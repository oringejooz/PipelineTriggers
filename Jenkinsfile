pipeline {
    agent any

    triggers {
        // Trigger the pipeline on any push to the 'main' branch
        githubPush()
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'python3 -m venv venv'  // Create virtual environment
                sh '. venv/bin/activate'   // Activate virtual environment
                sh 'pip install -r requirements.txt'  // Install dependencies
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pytest tests/test_app.py'  // Run the unit tests
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deploy steps here (e.g., pushing to server, AWS, etc.)
            }
        }
    }
}
