pipeline {
    agent {
        docker {
            image 'python:3.11'
        }
    }

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Swayang123/jenkins-python-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt || true'
            }
        }

        stage('Run Script') {
            steps {
                sh 'python script.py'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed. Clean up done.'
        }
    }
}
