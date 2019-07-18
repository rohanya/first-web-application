pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/rohanya/first-web-application.git', branch: 'master', credentialsId: 'rohanya')
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Code Analysis') {
      steps {
        withSonarQubeEnv('jenkins') {
          sh 'mvn clean package sonar:sonar'
        }
      }
    }
  }
}
