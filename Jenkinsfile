pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run') {
            steps {
                sh '''
                docker rm -f my-container || true
                docker run -d -p 8081:80 --name my-container my-app
                '''
            }
        }

    }
}
