pipeline {
  
  environment {
    registry = "vishwavk2021/docker"
    registryCredential = 'Bri!!iouser2021'
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
        sh  'docker build -t vishwavk2021/docker:$BUILD_NUMBER .'
        sh 'docker push vishwavk2021/docker:$BUILD_NUMBER'
     }
   }
  }
//     stage('image pull') {
//     steps{
//      script {
//       sudo 'docker run -d -p 8080:8080 --name mavenwebapp vishwavk2021/docker:latest'
//      }
//    }
//   }
    
 }
}
