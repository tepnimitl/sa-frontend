pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bash 'df -Ph'
                bash 'dnf install -y nodejs npm'
                echo "Building JS."
                npm install
                npm run build
                touch hello.txt
                ls $PWD/hello.txt
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
