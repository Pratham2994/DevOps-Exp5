pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building project...'
      }
    }
    stage('Test') {
      steps {
        sh '''
          python3 -m pip install --upgrade pip
          python3 -m pip install pytest
          pytest -q --junitxml=pytest-results.xml
        '''
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying project (simulated)...'
      }
    }
  }
  post {
    always {
      junit 'pytest-results.xml'
    }
  }
}
