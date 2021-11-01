pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {   
                sh python tests.py   
            }
        }
        stage('Build') {
            steps {
                 script { 
                env.DockerFile = DockerFiletemp
                sh sudo docker build -t alison . Dockerfiletemp
            }
        }
        stage('Deploy') {
            steps {
                echo ${DockerFile}
            }
        }
    }
}
