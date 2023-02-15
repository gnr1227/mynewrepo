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
        snykSecurity(snykInstallation: 'snyk', targetFile: 'go.mod', snykTokenId: 'snyk')
      }
    }

  }
  environment {
    name = 'narendra'
    branch = 'test'
  }
}