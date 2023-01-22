pipeline{
    agent any
     environment {
        registry = "public.ecr.aws/o2o0c3m3/docker"
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
                sh 'aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/o2o0c3m3'
                   //sh 'docker tag docker:latest public.ecr.aws/o2o0c3m3/docker:latest' 
                    sh 'docker push public.ecr.aws/o2o0c3m3/docker:latest'
                }     
            }
        }
    }
}