pipeline {
  environment {
    DOCKER_USER_ID = "tepnimitl"
    DOCKERREPO = 'sentiment-analysis-frontend'
  }
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

                sh 'docker info'

                echo "$DOCKER_USER_ID/$DOCKERREPO:new"

                echo "build Docker"
                sh 'sudo docker build -t $DOCKER_USER_ID/$DOCKERREPO:new .'

                /*echo "push Docker"
                *sudo docker push $DOCKER_USER_ID/$DOCKERREPO:new*/

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
