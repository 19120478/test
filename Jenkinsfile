pipeline {
    agent any
    stages {
        stage('Clone'){
            steps{
                git branch: 'main', credentialsId: 'f7e6ffda-26ad-4704-b935-dade04a63253', url: 'https://github.com/19120478/mmtnc-devops.git'
            }
        }
        stage('Build'){
            steps{
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    bat 'docker build -t 19120478/test:v1 .'
                    bat 'docker push 19120478/test:v1'
                }
            }
        }
    }
}