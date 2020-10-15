pipeline {
  environment {
    DOCKER_USER_ID = "tepnimitl"
    DOCKER_REPO = 'sentiment-analysis-frontend'
    registry = "$DOCKER_USER_ID/$DOCKER_REPO"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any

    stages {
        stage('Build App') {
            steps {
                echo 'Building..'
                sh 'sudo dnf install -y nodejs npm'
                echo "Building ReacJS.."
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Build Image') {
            steps {

                echo 'Build Docker'
                script {
                  dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }

                echo "Push Docker"
                script {
                  docker.withRegistry( '', registryCredential ) {
                    dockerImage.push()
                  }
                }

            }
        }
        stage('Test Image') {
            steps {
                echo 'Testing....'
                sh 'sudo docker images | grep $DOCKER_REPO | grep $BUILD_NUMBER'
            }
        }
        stage('Clean') {
            steps {
                echo 'Cleaning....'
                sh 'sudo docker rmi $registry:$BUILD_NUMBER'
            }
        }
    }
}
