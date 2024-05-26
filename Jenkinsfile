pipeline{
    agent any

    stages {
        stage('Clone Repository'){
            steps {
                sh '''
                rm -rf /var/lib/jenkins/workspace/flask-cicd
            git branch: 'development', credentialsId: '68d48143-7cac-43a3-a986-3ac6ecd8e2cc', url: 'https://github.com/Madhukar-Reddy-Katkuri/gcp-devops-project'
           }
        }
           
    }
}
