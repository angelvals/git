pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm run build'
          }
        }
        stage('') {
          steps {
            timeout(time: 10)
          }
        }
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}