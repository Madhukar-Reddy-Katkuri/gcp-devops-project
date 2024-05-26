pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'development', url: 'https://github.com/Madhukar-Reddy-Katkuri/gcp-devops-project.git'
            }
        }

        stage('Set up environment') {
            steps {
                script {
                    def pythonEnv = "python3 -m venv venv"
                    def activate = "source venv/bin/activate"

                    sh "${pythonEnv}"
                    sh "${activate} && pip install -r requirements.txt"
                }
            }
        }

        stage('Run tests') {
            steps {
                script {
                    def activate = "source venv/bin/activate"
                    sh "${activate} && python -m unittest discover -s tests"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def activate = "source venv/bin/activate"
                    sh "${activate} && nohup python app.py &"
                }
            }
        }
    }

    post {
        always {
            script {
                // Clean up virtual environment
                sh "rm -rf venv"
            }
        }
    }
}
