pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/rohanya/first-web-application.git', branch: 'master', credentialsId: 'rohanya')
      }
    }
  }
}