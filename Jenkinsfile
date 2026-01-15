pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                cd flask-backend || true
                pip3 install -r requirements.txt
                '''
            }
        }

        stage('Restart Flask') {
            steps {
                sh 'pm2 restart flask-app || pm2 start app.py --name flask-app'
            }
        }
    }
}

