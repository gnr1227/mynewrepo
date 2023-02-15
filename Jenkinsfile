pipeline {
  agent any
  stages {
    stage('git checkout') {
      steps {
        sh 'whoami;date;hostname'
        git(url: 'https://github.com/dragonflyoss/Dragonfly2.git', branch: 'main')
      }
    }

    stage('snyk check') {
      steps {
        sh '/var/jenkins_home/snyk monitor --file=go.mod --token=$SNYK_TOKEN'
      }
    }

  }
  environment {
    name = 'narendra'
    branch = 'test'
  }
}