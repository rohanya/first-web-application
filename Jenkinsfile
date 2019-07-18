pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/rohanya/first-web-application.git', branch: 'master', credentialsId: 'rohanya')
      }
    }
  }
}