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
        sh '''

printf "Waiting for $HOST:$PORT"
until nc -z $localhost $8088 2>/dev/null; do
    printf \'.\'
    sleep 10
done
echo "up!"
'''
      }
    }

  }
}