pipeline {

    agent any
    environment{
        DOCKERHUB_CREDENTIALS=credentials('dockerhublogin')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kodingkahawa/CICD-Pipeline-Jenkins-GitHub-and-Docker.git']]])
            }
        }
    
        stage('Build') {
            steps {
                sh 'docker build -t oyaro/test:latest'
            }
        }

        stage('Docker hub login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
    
        stage('Push Image') {
            steps {
                sh 'docker push oyaro/test:latest'
            }
        }
    }
} 
