pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
        emailext(to: 'Developer_1', subject: 'Develop complete', body: 'Develop phase is completed', from: 'admin')
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}