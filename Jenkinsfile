pipeline {
    agent any
    environment {
        PATH = "/home/bsalokye/.local/bin:${env.PATH}"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/salokye3/Jenkins-test'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m pip install --user -r requirements.txt
                '''
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                pytest tests/
                '''
            }
        }
    }
}

