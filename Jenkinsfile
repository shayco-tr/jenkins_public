pipeline {
    agent any
    parameters {
        string(name: 'DockerFile', defaultValue: 'DockerFiletemp')
    }
    stages {
        stage('Test') {
            steps {
                script {   
                sh 'python tests.py'   
            }
        }
        stage('Build') {
            steps {
                sh 'sudo docker build -t alison . -f Dockerfiletemp'
            }
        }
        stage('Deploy') {
            steps {
                 echo ${params.DockerFile}
            }
        }
    }
