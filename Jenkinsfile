pipeline {
  agent any
tools {
  nodejs 'Node18'  // Or whatever name you used
       }
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
        sh 'npm install'
        echo 'Installing dependencies...'
        // Ensure Playwright is installed
        sh 'npx playwright install-deps'
        echo 'Installing Playwright dependencies...'
        // Install Node.js dependencies
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
