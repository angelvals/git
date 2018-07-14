pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
        emailext(subject: 'Build - Developer', body: 'Build Successfull', attachLog: true, to: 'Developer_1')
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
}