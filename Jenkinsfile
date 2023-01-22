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
    }
}