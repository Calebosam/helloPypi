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
          git config --global user.email "$(git log -n 1 --pretty=format:%ae)"
          git config --global user.name "$(git log -n 1 --pretty=format:%an)"
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
 