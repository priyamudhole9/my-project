pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/priyamudhole9/my-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run') {
            steps {
                sh '''
                docker rm -f my-container || true
                docker run -d -p 8080:80 --name my-container my-app
                '''
            }
        }

    }
}
