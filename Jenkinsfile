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

    stage('Configure git') {
      steps {
        sh """
          git config --global user.email caleb.osam@amalitech.com
          git config --global user.name Calebosam
          git config -l
        """
      }
    }

    stage('Push to github') {
      steps {
            // sh 'git push --follow-tags origin HEAD'
          sh 'echo PyPi'
          
         }
    }

    stage('Deploy To PyPi') {
      steps {
          sh 'echo PyPi2'
        }
    }
  }
}
 