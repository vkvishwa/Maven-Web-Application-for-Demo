pipeline {
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
    stage("sonarqube stage"){
       steps {
         sh "mvn package sonar:sonar"
       }
    }
  }
}
