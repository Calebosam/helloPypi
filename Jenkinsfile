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
          pip3 install wheel
        """
      }
    }

    stage('Configure git') {
      steps {
        sh """
          git config --global user.email caleb.osam@amalitech.com
          git config --global user.name Calebosam
        """
      }
    }

    stage('Build Package') {
      steps {
        sh """
          python3 setup.py sdist bdist_wheel
          /home/jenkins/.local/bin/bump
        """
      }
    }

    stage('Push to github') {
      steps {
        sh 'git push origin main'
      }
    }

    stage('Deploy To PyPi') {
      steps {
        sh 'echo PyPi2'
      }
    }
  }
}
 