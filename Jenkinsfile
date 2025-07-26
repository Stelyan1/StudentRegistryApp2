pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/Stelyan1/StudentRegistryApp2.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        bat 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        bat 'npm test'
      }
    }

  }

  post {
    success {
      echo 'CI passed!'
    }
    failure {
      echo 'CI failed!'
    }
  }
}