pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        Checkout scm
      }
    }
    stage('Build') {
      steps {
        echo 'checking pyhton application'
        bat 'python -m py_compile app.py'
      }
    }
    stage('Test') {
      steps {
        echo 'executing automated tests'
        bat 'python -m unittest app'
      }
    }

    stage('Run application') {
      steps {
        bat 'python app.py'
      }
    }
    post {
      success{
        echo 'CI pipeline completed successfully'
      }
      failure {
        echo 'CI pipeline failed'
      }
    }
  }
