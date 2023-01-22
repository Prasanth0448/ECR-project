pipeline{
    agent any
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