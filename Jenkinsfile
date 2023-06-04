pipeline {
  agent {
        label 'jenkins-node-python-agent'
    }
  stages {
        stage('Install Build tools') {
            steps {
            sh """
              python3 -m pip install --upgrade build
              pip3 install twine
              pip3 install bump
            """
            }
        }
        stage('Build Package') {
            
            steps {
                sh """
                git --version
                """
            }
        }
     stage('Deploy To PyPi') {
       steps {
            sh 'python3 --version'
         }
       }
     }
 }
 