pipeline {
  agent any
  stages {
    stage('Install') {
      agent {
        node {
          label 'bat'
        }

      }
      steps {
        sh 'npm install'
      }
    }
  }
}