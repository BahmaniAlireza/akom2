pipeline {
  agent {
    kubernetes {
      // this label will be the prefix of the generated pod's name
      label 'jenkins-agent-my-app'
      yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    jenkins: slave
spec:
  containers:
    - name: docker
      image: docker:latest
      command:
        - cat
      tty: true
      volumeMounts:
        - mountPath: /var/run/docker.sock
          name: docker-sock
  volumes:
    - name: docker-sock
      hostPath:
        path: /var/run/docker.sock
"""
    }
  }
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
