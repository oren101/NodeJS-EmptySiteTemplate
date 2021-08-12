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
        sh '''node server.js &
sleep 5 &&
curl localhost:8088
if [[ "x$?" == "x0" ]];
then echo good;
else exit 1;
fi
'''
      }
    }

  }
}