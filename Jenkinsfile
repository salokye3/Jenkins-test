pipeline {
    agent any
    environment {
        PATH = "${env.PATH}:${env.HOME}/.local/bin"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/salokye3/Jenkins-test'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                export PATH=$PATH:$HOME/.local/bin
                pytest tests/
                '''
            }
        }
    }
}

