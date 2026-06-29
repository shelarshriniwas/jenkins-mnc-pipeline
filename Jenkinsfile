pipeline {

    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    environment {
        APP_NAME = "Python Demo"
        PYTHON = "python3"
    }

    stages {

        stage('Checkout') {
            steps {
                echo "Checkout Source Code"
            }
        }

        stage('Environment Info') {
            steps {
                sh '''
                pwd
                whoami
                hostname
                python3 --version
                '''
            }
        }

        stage('Create Virtual Environment') {
            steps {
                sh '''
                python3 -m venv venv
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Application') {
            steps {
                sh '''
                . venv/bin/activate
                python app.py
                '''
            }
        }

        stage('Run Unit Test') {
            steps {
                sh '''
                . venv/bin/activate
                pytest -v
                '''
            }
        }

    }

    post {

        always {
            echo "Pipeline Finished"
        }

        success {
            echo "Build Successful"
        }

        failure {
            echo "Build Failed"
        }
    }
}
