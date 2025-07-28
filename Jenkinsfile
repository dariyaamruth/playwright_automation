pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        // git url: 'https://github.com/dariyaamruth/playwright_automation.git'
      }
    }

    stage('Install') {
      steps {
        sh 'npm ci'
      }
    }

    stage('Test') {
      steps {
        sh 'npx playwright test'
      }
    }
  }
}
