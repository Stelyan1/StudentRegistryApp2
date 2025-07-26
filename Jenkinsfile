pipeline {
  agent any

  tools {
    nodejs "NodeJS" // Use the Node.js installation configured in Jenkins (Manage Jenkins > Global Tool Configuration)
  }

  stages {
    stage('Checkout') {
      steps {
        // Pull code from GitHub
        git url: 'https://github.com/Stelyan1/StudentRegistryApp2', branch: 'master'
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

    stage('Start Application') {
      steps {
        sh 'npm start & sleep 5'  // Run in background temporarily for verification
        // Optionally add curl or health check logic here
      }
    }
  }

  post {
    success {
      echo '✅ Build completed successfully.'
    }
    failure {
      echo '❌ Build failed.'
    }
  }
}