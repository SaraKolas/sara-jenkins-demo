pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker build -t sara/demo-app:latest .'
                }
            }
        }

        stage('Success Message') {
            steps {
                echo 'Build Successful!'
            }
        }
    }
}
