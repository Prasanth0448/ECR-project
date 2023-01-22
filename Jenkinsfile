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
        stage('Tag image on ECR'){
            steps{
              script {
                    sh 'docker tag docker:latest public.ecr.aws/o2o0c3m3/docker:latest' 
                }     
            }
        }
    }
}