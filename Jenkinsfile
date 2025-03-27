pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Srikar2610/python-docker-app.git'
            }
        }

        stage('Install Dependencies') {
    steps {
        sh '''
        python3 -m venv venv
        bash -c "source venv/bin/activate && pip install -r requirements.txt"
        '''
    }
}


        stage('Run Tests') {
            steps {
                sh 'pytest tests/'
            }
        }
    }
}
