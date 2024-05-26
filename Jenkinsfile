pipeline{
    agent any
    environment {
        JOB_NAME = 'flask-cicd'
    }

    stages {
        stage('Remove existing repository'){
            steps {
                sh '''
                rm -rf /var/lib/jenkins/workspace/("${env.IMAGE_NAME}")
               
                '''
            }
        }
        stage('Clone Repository'){
            steps {
            git branch: 'development', credentialsId: '68d48143-7cac-43a3-a986-3ac6ecd8e2cc', url: 'https://github.com/Madhukar-Reddy-Katkuri/gcp-devops-project'
           }
        }
           
    }
}
