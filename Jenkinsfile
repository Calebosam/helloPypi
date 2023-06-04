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
          git checkout main
          /home/jenkins/.local/bin/bump
          git add .
          git commit -m 'create new version'
        """
        withCredentials([gitUsernamePassword(credentialsId: 'Calebosam', gitToolName: 'Default')]) {
          sh "git push origin main"
        }
      }
    }

    stage('Deploy To PyPi') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'pypi-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
          sh "twine upload --username $USERNAME --password $PASSWORD dist/*"
        }
      }
    }
  }
}
 