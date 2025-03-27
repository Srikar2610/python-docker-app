pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
    git branch: 'main', 
        credentialsId: 'github-id',
        url: 'https://github.com/Srikar2610/python-docker-app.git'
}

        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    source venv/bin/activate
                    pytest tests/
                '''
            }
        }
    }
}
