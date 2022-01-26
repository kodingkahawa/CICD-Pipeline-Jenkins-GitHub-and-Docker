pipeline {

    agent any
    environment{
        DOCKERHUB_CREDENTIALS=credentials('dockerhublogin')
    }

    stages {
        stage('Checkout') {
            steps {
                sh 'git https://github.com/kodingkahawa/CICD-Pipeline-Jenkins-GitHub-and-Docker.git'
            }
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t oyaro/test:latest'
            }
        }
    }
    stages {
        stage('Docker hub login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
    }
    stages {
        stage('Push Image') {
            steps {
                sh 'docker push oyaro/test:latest'
            }
        }
    }
    post {
        always{
            sh 'docker logout'
        }
    }   
}