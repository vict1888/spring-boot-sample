pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }
    stage('test') {
      steps {
        sh 'mvn test'
        junit 'target/surefire-reports/*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
    stage('Deploy') {
      steps {
        sh 'make deploy-default'
      }
    }
  }
}