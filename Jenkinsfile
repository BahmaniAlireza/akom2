pipeline {
  agent any
  stages {
    stage('stage2') {
      steps {
        sh 'echo "aaaaa"'
      }
    }
    stage('stage3') {
      steps {
        sh '''echo "3333"
sleep 30
'''
      }
    }
    stage('stage4') {
      steps {
        sh '''echo "4444"
sleep 30'''
      }
    }
  }
}