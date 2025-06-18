pipeline {
  agent any
  tools {
    nodejs 'NodeJS 18.20.0' // Use the name you configured
  }
  stages {
    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }
    stage('Run Playwright Tests') {
      steps {
        sh 'npx playwright install --with-deps'
        sh 'npx playwright test'
      }
    }
  }
}
