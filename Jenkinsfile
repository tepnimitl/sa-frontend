pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bash 'df -Ph'
                bash 'dnf install -y nodejs npm'
                bash 'echo "Building JS."'
                bash 'npm install'
                bash 'npm run build'
                bash 'touch hello.txt'
                bash 'ls $PWD/hello.txt'
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
