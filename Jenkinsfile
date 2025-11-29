pipeline {
  agent any
//   tools {
//     go 'go-1.25.4'
//   }

  environment {
    GO111MODULE = 'on' //YOU MUST set this to 'on' to use Go Modules
  }
  stages {
    stage('Test') {
      steps {
        git 'https://github.com/natanaeldev/go-webapp-sample.git'
        sh 'go test ./...'
      }
    }
    stage('Build') {
      steps {
        script {
           git 'https://github.com/natanaeldev/go-webapp-sample.git'
           sh 'go build'
        }
      }
    }
    stage('Run') {
      steps {
        script {
          sh 'cd /var/lib/jenkins/workspace/go-full-pipeline && ./go-webapp-sample &'
        }
      }
    }

  }
}