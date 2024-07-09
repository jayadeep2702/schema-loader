pipeline {
    agent {
        node {
            label 'workstation'
        }
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 710990938946.dkr.ecr.us-east-1.amazonaws.com'
                sh 'docker build -t 710990938946.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest .'
                sh 'docker push 710990938946.dkr.ecr.us-east-1.amazonaws.com/schema-loader:latest'
            }
        }

    }

}