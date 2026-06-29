pipeline {

    agent any

    stages {

        stage('Install Dependencies') {

            steps {

                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''

            }

        }

        stage('Run Application') {

            steps {

                sh '''
                python3 app.py
                '''
            }

        }

    }

}
