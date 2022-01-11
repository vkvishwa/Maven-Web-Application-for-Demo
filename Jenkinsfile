pipeline {
  agent any
  stages {
     stage("Cleaning Stage") {
      steps {
        bat "mvn clean"
      }
    }
    stage("Testing stage") {
      steps {
        bat "mvn test"
      }
    }
    stage("Packaging stage") {
      steps {
        bat "mvn package"
      }
    }
    
    stage("Building image"){
      steps {
        bat "docker build -t vishwavk2021/docker:latest ."
      }
    }
  }
}
