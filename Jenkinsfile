pipeline {
    environment{
        dockerimagename = "oyaro/testapp"
        dockerImage = ""
    
    }
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kodingkahawa/CICD-Pipeline-Jenkins-GitHub-and-Docker.git']]])
            }
    
        stage('Build') {
            steps {
                script{
                    dockerImage = docker.build dockerimagename
                }

            }
        }
        stage('Push Image') {
            environment {
               registryCredential = 'dockerhublogin'
           }
            steps{
                script {
                    docker.withRegistry( 'https://hub.docker.com/', registryCredential ) {
                        dockerImage.push("latest")
                    }
                }
            }
        }
    }
}    