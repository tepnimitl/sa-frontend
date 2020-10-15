pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                df -Ph
                bash 'dnf install -y nodejs npm'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
