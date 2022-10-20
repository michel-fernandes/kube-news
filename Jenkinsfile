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

    }
}