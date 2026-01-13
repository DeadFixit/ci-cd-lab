pipeline {
  agent any

  stages {
    stage('Install') {
      steps {
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
        sh 'pytest'
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t ci-app .'
      }
    }

    stage('SonarQube') {
      steps {
        sh 'echo "Sonar scan placeholder"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "Deploy placeholder"'
      }
    }
  }
}
