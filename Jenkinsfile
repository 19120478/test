pipeline {
    agent any
    stages {
        stage('Clone'){
            steps{
                //bat "rmdir /s /q test mmtnc-devops"
                bat "git clone https://github.com/19120478/mmtnc-devops.git"
            }
        }
        stage('Build'){
            steps{
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    bat 'docker build -t 19120478/Devops:v1 .'
                    bat 'docker push 19120478/Devops:v1'
                }
            }
        }
    }
}