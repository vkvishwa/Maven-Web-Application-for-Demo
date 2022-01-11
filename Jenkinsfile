pipeline {
  
  environment {
    registry = "vishwavk2021/docker"
    registryCredential = 'Bri!!Iouser2021'
    dockerImage = ''
  }
  
  agent any
  stages {
     stage("Cleaning Stage") {
      steps {
        sh "mvn clean"
      }
    }
    stage("Testing stage") {
      steps {
        sh "mvn test"
      }
    }
    stage("Packaging stage") {
      steps {
        sh "mvn package"
      }
    }
  stage('Building our image') {
    steps{
     script {
      dockerImage = docker.build registry + ":$BUILD_NUMBER"
     }
   }
  }
 }
}
