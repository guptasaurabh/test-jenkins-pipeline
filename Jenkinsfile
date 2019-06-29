pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/guptasaurabh/test-jenkins-pipeline'
      }
    }
    stage('Sphinx Deploy') {
      steps {
        build 'Test'
      }
    }
    stage('Tests') {
      steps {
        build 'Test'
        build 'TestFail'
      }
    }
  }
}