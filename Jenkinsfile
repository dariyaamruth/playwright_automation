pipeline {
  agent any

  // NodeJS tool configuration is not supported here; use the 'tool' step in the pipeline steps instead.
  
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
    stage('Install') {
      steps {
        script {
          def nodeHome = tool name: 'Node18', type: 'hudson.plugins.nodejs.tools.NodeJSInstallation'
          env.PATH = "${nodeHome}/bin:${env.PATH}"
        }
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
      steps {
        sh 'npx playwright test'
      }
    }
  }
}
