pipeline {
    agent any

    triggers {
   
        githubPush()
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'python3 -m venv venv'  
                sh '. venv/bin/activate'   
                sh 'pip install --break-system-packages -r requirements.txt'
 
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 -m pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }
}
