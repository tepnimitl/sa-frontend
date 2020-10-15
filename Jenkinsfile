pipeline {
    agent any

    stages {
        stage('Build App') {
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
        stage('Build Image') {
            /* docker build on command line */
            steps {
                echo 'Testing..'
                docker.build("tepnimitl/sentiment-analysis-frontend")
            }
        }
        stage('Test Image') {
            steps {
                echo 'Testing....'
                sh 'echo "Test Passed"'
            }
        }stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
