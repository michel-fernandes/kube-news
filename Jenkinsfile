pipeline {
    agent any

    stages {

        stage ('Build docker Inage'){
            steps{
                script{
                    dockerapp = docker.build("michelfernandes/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }

        stage('Push Docker Image'){
            steps{
                script{
                    docker.withRegistry('https://registryhub.docker.com', 'dockerhub'){
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

    }
}