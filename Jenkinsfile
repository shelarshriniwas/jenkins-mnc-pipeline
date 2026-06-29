pipeline {

    agent any

    stages {

        stage('Install Dependencies') {

            steps {

                sh '''
                python3 -m pip install --upgrade pip
                pip3 install -r requirements.txt
                '''

            }

        }

        stage('Run Application') {

            steps {

                sh '''
                python3 hello.py
                '''
            }

        }

    }

}
