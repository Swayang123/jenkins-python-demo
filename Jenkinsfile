pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git url: 'git 'https://github.com/Swayang123/jenkins-python-demo.git'
'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt || true'
            }
        }

        stage('Run Script') {
            steps {
                sh 'python3 script.py'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed. Clean up done.'
        }
    }
}
