pipeline {
  agent any

  // NodeJS tool configuration is not supported here; use the 'tool' step in the pipeline steps instead.
  tools {
    nodejs 'Node23' // Ensure this matches the Node.js version installed on your Jenkins
  }
  stages {
    stage('Clone') {
      steps {
        // Uncomment the following line if you want to clone a specific repository
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/dariyaamruth/playwright_automation.git'
        echo 'Cloning repository...'
      }
    }

    stage('Install') {
      steps {
        sh 'npm install'
        sh 'pip install --upgrade pip'
        sh 'pip install pytest pytest-playwright'
        sh 'pip install playwright'
        sh 'python3.10 -m playwright install'
        // sh 'playwright install-deps'
        // Ensure that the Playwright browsers are installed
        sh 'playwright install chromium firefox webkit'
        // Install Node.js dependencies
        sh 'npm ci'
        sh 'pytest --tracing=retain-on-failure'
      }
    }

    stage('Test') {
      steps {
        sh 'npx playwright test'
      }
    }
  }
}
