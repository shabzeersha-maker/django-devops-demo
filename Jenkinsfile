pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/shabzeersha-maker/django-devops-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Django') {
            steps {
                sh '''
                . venv/bin/activate
                python manage.py migrate
                python manage.py runserver 0.0.0.0:8000
                '''
            }
        }
    }
}
