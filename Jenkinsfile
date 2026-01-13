pipeline {
  agent any

  stages {
    stage('Install') {
      steps {
        sh 'python3 -m pip install -U pip'
        sh 'pip3 install -r requirements.txt'
      }
    }

    stage('Lint') {
      steps {
        sh 'flake8 app.py || true'
      }
    }

    stage('Test') {
      steps {
        sh 'pytest -q'
      }
    }
  }
}
