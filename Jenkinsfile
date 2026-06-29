pipeline {

    agent any

    stages {

        stage('Install Dependencies') {

            steps {

                sh '''
                python3 -m pip install -r requirements.txt
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
