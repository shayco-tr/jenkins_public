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
                sh docker build -t alison . -f Dockerfiletemp
            }
        }
        stage('Deploy') {
            steps {
                echo ${DockerFile}
            }
        }
    }
}
