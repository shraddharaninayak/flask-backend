pipeline {
    agent any

    stages {
        stage('Deploy Flask') {
            steps {
                sh '''
                echo "Workspace path: $WORKSPACE"
                python3 --version

                # create venv if not exists
                if [ ! -d "venv" ]; then
                  python3 -m venv venv
                fi

                . venv/bin/activate
                pip install -r requirements.txt

                pm2 restart flask-app || pm2 start app.py --name flask-app --interpreter ./venv/bin/python
                '''
            }
        }
    }
}



