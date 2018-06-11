pipeline {
  agent any
  stages {
    stage('Compile') {
      parallel {
        stage('Compile') {
          steps {
            sh 'make'
          }
        }
        stage('Install Java') {
          steps {
            sh 'yum install java'
          }
        }
      }
    }
    stage('Test') {
      steps {
        sh 'make test'
      }
    }
    stage('packaging') {
      steps {
        archiveArtifacts 'git*'
      }
    }
  }
}