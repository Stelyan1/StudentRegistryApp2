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
        sh 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'npm test'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
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