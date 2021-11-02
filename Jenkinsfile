pipeline {
    agent any
    parameters {
        string(name: 'DockerFile', defaultValue: 'DockerFiletemp')
    }
    stages {
        stage('Test') {
            steps {
               sh ''' echo \'installing libs\'
                pip3 install .
                echo \'running tests\'
                python3 tests.py ''' 
            }
        }
        stage('Build') {
            steps {
                sh """ echo 'building docker image'
                echo ${params.Dockerfile}
                sudo docker build -t alison . -f ${params.Dockerfile} """
            }
        }
        stage('Deploy') {
            steps {
                 echo "${params.DockerFile}"
            }
        }
    }
  }
