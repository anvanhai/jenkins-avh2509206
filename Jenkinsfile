pipeline {
  agent any
  triggers { pollSCM('H/2 * * * *') }
  stages {
    stage('Jenkins thay commit') {
      steps {
        sh 'git log -1 --oneline'
      }
    }
  }
}