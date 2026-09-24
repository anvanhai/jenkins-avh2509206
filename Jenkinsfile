pipeline {
  agent any
  triggers { pollSCM('H/2 * * * *') }
  environment {
    VERCEL_TOKEN      = credentials('vercel-token')
    VERCEL_ORG_ID     = credentials('vercel-org-id')
    VERCEL_PROJECT_ID = credentials('vercel-project-id')
  }
  stages {
    stage('Jenkins thay commit') {
      steps {
        bat 'git log -1 --oneline'
      }
    }
    stage('Deploy Vercel') {
      steps {
        bat 'npx.cmd vercel deploy --prod --yes --token %VERCEL_TOKEN%'
      }
    }
  }
}