pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh 'echo ok'
      }
    }
    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Delivery') {
      steps {
        sh './jenkins/scripts/deliver.sh'
      }
    }
    stage('1') {
      steps {
        input 'Finished using the web site? (Click "Proceed" to continue)'
      }
    }
    stage('2') {
      steps {
        sh './jenkins/scripts/kill.sh'
      }
    }
  }
}