pipeline {
    agent any

    stages {
        stage('Deploy Flask') {
            steps {
                sh '''
                cd /home/ubuntu/flask-backend
                git pull origin main
                pm2 restart flask-app
                '''
            }
        }
    }
}


