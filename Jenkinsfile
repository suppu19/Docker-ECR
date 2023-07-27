pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="492840825928"
        AWS_DEFAULT_REGION="ap-south-1" 
        IMAGE_REPO_NAME="niznix-image"
        IMAGE_TAG="latest"
        REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"
    }
     stages {
         stage('Logging into AWS ECR') {
            steps {
                script {
                    sh "aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 492840825928.dkr.ecr.ap-south-1.amazonaws.com"
           }
        }
    }        
        stage("Build the docker image"){
                steps {
                    sh "docker build -t ${IMAGE_REPO_NAME} ."
                    sh "docker tag niznix-image:latest 492840825928.dkr.ecr.ap-south-1.amazonaws.com/niznix-image:latest"
                    sh "docker push 492840825928.dkr.ecr.ap-south-1.amazonaws.com/niznix-image:latest"
                    
                }
            } 
    }
}
         

