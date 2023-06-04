pipeline {
  agent {
        label 'jenkins-node-python-agent'
    }
  stages {
        stage('Install Build tools') {
            steps {
            sh 'echo Hello'
            }
        }
        stage('Build Package') {
            
            steps {
                sh 'echo hello world'
            }
        }
     stage('Deploy To PyPi') {
       steps {
            sh 'python3 --version'
         }
       }
     }
 }
 