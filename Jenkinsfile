pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/<your-username>/flask-backend.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Restart Flask') {
            steps {
                sh 'pm2 restart flask-app || pm2 start app.py --name flask-app --interpreter python3'
            }
        }
    }
}
