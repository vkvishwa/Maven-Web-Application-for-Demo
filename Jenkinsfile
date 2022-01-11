pipeline {
  
  environment {
    registry = "docker_hub_account/repository_name"
    registryCredential = 'dockerhub'
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
//     stage("sonarqube stage"){
//        steps {
//          sh "mvn package sonar:sonar"
//        }
//     }
   stages {
  stage('Building image') {
    steps{
      script {
        docker.build registry + ":$BUILD_NUMBER"
      }
    }
  }
}
    }
  }
}
