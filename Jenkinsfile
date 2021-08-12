pipeline {
  agent any
  stages {
    stage('Check Out Code') {
      steps {
        git(url: 'https://github.com/oren101/NodeJS-EmptySiteTemplate.git', branch: 'master', changelog: true, poll: true)
      }
    }

    stage('Build') {
      steps {
        sh 'npm install '
      }
    }

    stage('Test Code') {
      steps {
        sh 'node server.js .'
      }
    }

  }
}