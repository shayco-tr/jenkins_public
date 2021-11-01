pipeline {
    agent any
    parameters {
        string(name: 'DockerFile', defaultValue: 'DockerFiletemp')
    }
    stages {
        stage('Test') {
            steps {   
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
  }
