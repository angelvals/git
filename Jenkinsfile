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
        emailext(subject: 'Build - Developer', body: 'Build Completed', attachLog: true, to: 'Developer_1')
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
        emailext(subject: 'Testing', body: 'Testing App, please approve', from: 'admin', attachLog: true, to: 'Tester_1')
        input(id: '1', message: 'Approve testing')
      }
    }
    stage('Release') {
      steps {
        sh '''git add .
git commit -am "Release"
git push origin master'''
        waitUntil()
      }
    }
  }
}