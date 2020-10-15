pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'df -Ph'
                sh 'sudo dnf install -y nodejs npm'
                sh 'echo "Building JS."'
                sh 'npm install'
                sh 'npm run build'
                sh 'touch hello.txt'
                sh 'ls $PWD/hello.txt'
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
