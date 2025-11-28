pipeline {
  agent any
//   tools {
//     go 'go-1.25.4'
//   }

  environment {
    GO111MODULE = 'on' //YOU MUST set this to 'on' to use Go Modules
  }
  stages {
    stage('Development') {
      steps {
        git 'https://github.com/natanaeldev/go-webapp-sample.git'
        // sh 'go test ./...'
      }
    }
    stage('Building our image') {
      steps {
        script {
          app = docker.build("natanaeldev/go-webapp-sample")
        }
      }
    }

  }
}