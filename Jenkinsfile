pipeline {
  agent any
  stages {
        stage('Install Build tools') {
            steps {
            sh 'python --version'
            }
        }
        stage('Build Package') {
            
            steps {
                sh 'echo hello world'
            }
        }
     stage('Deploy To PyPi') {
       steps {
            sh 'echo hello2'
         }
       }
     }
 }
 