pipeline {
    agent any

    stages {
        stage('AWS VALIDATE') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('AWS S3 listar') {
            steps {
                sh 'aws s3 ls'
            }
        } 
        stage('Git Clone') {
            steps {
                sh 'rm -rf Jenkins/'
                sh 'git clone https://github.com/javiergiuga/Jenkins.git'
                sh 'ls -lrt Jenkins/'
            }
        } 
        stage('Upload to S3') {
            steps {
                sh 'aws s3 cp Jenkins s3://jenkins-giu--recursive'
            }
        }         
    }
}
