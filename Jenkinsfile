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
      parallel {
        stage('Tests') {
          steps {
            build(job: 'Test', propagate: true)
            build(job: 'TestFail2', propagate: true)
          }
        }
        stage('Integration Test') {
          steps {
            build(job: 'TestFail', propagate: true)
          }
        }
      }
    }
  }
}