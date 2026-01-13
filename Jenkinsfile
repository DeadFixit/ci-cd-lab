pipeline {
  agent {
    docker {
      image 'python:3.12-slim'
      args '-u root:root'
    }
  }

  stages {
    stage('Install') {
      steps {
        sh 'python -m pip install -U pip'
        sh 'pip install -r requirements.txt'
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
