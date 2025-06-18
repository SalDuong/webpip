pipeline {
  agent any
  stages {
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
        archiveArtifacts artifacts: 'playwright-report/**', fingerprint: true
      }
    }
  }
}
