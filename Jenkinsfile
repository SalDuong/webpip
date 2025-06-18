
pipeline {
  agent {
    // Use the official Playwright Docker image for consistency
    docker { image 'mcr.microsoft.com/playwright:v1.49.1-jammy' }
  }

  options {
    timeout(time: 60, unit: 'MINUTES') // Set job timeout to 60 minutes
  }

  stages {
    stage('Checkout') {
      steps {
        // Clone your repository
        checkout scm
      }
    }
    stage('Install Dependencies') {
      steps {
        sh 'npm ci'
        sh 'npx playwright install --with-deps'
      }
    }
    stage('Run Playwright tests') {
      steps {
        sh 'npx playwright test'
      }
    }
    stage('Archive Playwright Report') {
      steps {
        // Archive the test report as a build artifact
        archiveArtifacts artifacts: 'playwright-report/**', fingerprint: true
      }
    }
  }
}
