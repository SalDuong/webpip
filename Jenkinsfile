
pipeline {

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
