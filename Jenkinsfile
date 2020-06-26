pipeline {
  agent any
  /*environment {
    //registryCredential = 'dockerhub'
   }*/
  stages {
    stage('Build') {
      steps {
          echo 'Hello Build'
          //sh 'docker build -t mustafa75/test-image .'
      }
     }
    stage('Test') {
      steps {
          echo 'Hello test'
          //sh 'docker container run -p 9090:8080 --name node -d mustafa75/test-image'
          //sh 'curl -I http://localhost:9090'
      }
    }
    stage('Publish') {
      steps{
          echo 'Hello Publish'
        /*script {
        docker.withRegistry( '', registryCredential ) {
        sh 'docker push mustafa75/test-image:latest'
          }
        }*/
      }
    }
  }
}
