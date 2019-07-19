pipeline {
  agent any
  stages {
    stage('Git') {
      parallel {
        stage('Git') {
          steps {
            git(url: 'https://github.com/rohanya/first-web-application.git', branch: 'master', credentialsId: 'rohanya')
          }
        }
        stage('Git Dev') {
          steps {
            git(url: 'https://github.com/rohanya/first-web-application.git', branch: 'dev', changelog: true, credentialsId: 'rohanya', poll: true)
          }
        }
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