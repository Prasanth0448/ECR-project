pipeline{
    agent any
     environment {
        registry = "288524485830.dkr.ecr.us-east-1.amazonaws.com/docker"
    }
    stages{
        stage('build'){
            steps{
              script {
                     dockerImage = docker.build registry
                }     
            }
        }
        stage('Tag and push image on ECR'){
            steps{
              script {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 288524485830.dkr.ecr.us-east-1.amazonaws.com'
                   
                sh 'docker push 288524485830.dkr.ecr.us-east-1.amazonaws.com/docker:latest'
                }     
            }
        }
        stage('Docker Run') {
             steps{
               script {
                sh 'docker run -d -p 8096:5000 --rm --name mypythonContainer 288524485830.dkr.ecr.us-east-1.amazonaws.com/docker:latest'
               }
           }
        }
    }
}