pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="492840825928"
        AWS_DEFAULT_REGION="ap-south-1" 
        IMAGE_REPO_NAME="Docker-ECR"
        IMAGE_TAG="latest"
        REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"
    }
    stages {
         stage('Logging into AWS ECR') {
            steps {
                script {
                sh "aws ecr get-login-password - region ${AWS_DEFAULT_REGION} | docker login - hari401 AWS - password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com"
            }
            
        }

    }
}
}