pipeline {
  agent any

  environment {
    VENV = ".venv"
  }

  stages {
    stage('Install') {
      steps {
        sh 'python3 -m venv $VENV'
        sh '. $VENV/bin/activate && python -m pip install -U pip'
        sh '. $VENV/bin/activate && pip install -r requirements.txt'
      }
    }

    stage('Lint') {
      steps {
        sh '. $VENV/bin/activate && flake8 app.py || true'
      }
    }

    stage('Test') {
      steps {
        sh '. $VENV/bin/activate && pytest -q'
      }
    }
  }
}
