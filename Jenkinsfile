pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        // git url: 'https://github.com/dariyaamruth/playwright_automation.git'
      // Uncomment the above line to clone the repository
        echo 'Cloning repository...'
      }
    }

    stage('Install') {
      steps {
        sh
        sh 'npm ci'
        sh 'npx playwright install'
        echo 'Dependencies installed.'
      }
    }

    stage('Test') {
      steps {
        sh 'npx playwright test'
      }
    }
  }
}
