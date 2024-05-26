pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
            echo 'build docker image'
            sh '''
            cd  jenkins-multibranch-pipeline_dev
            docker build -t flask:v1 .
            '''
          }
        }

        stage('Deploy the image') {
            steps{
            sh '''
            docker run -d -p 5001:5000 flask:v1
            ''' 
            }
        }
        
    }
}