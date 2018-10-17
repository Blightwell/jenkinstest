pipeline {
  environment {
    registry = "choapinus/docker-ribbit"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  tools {python "python"}
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://gitlab.com/Choapinus/t1_arqsist'
      }
    }
    stage('Build') {
       steps {
         sh 'python manage.py runserver 0:8081'
       }
    }
    stage('Test') {
      steps {
        echo 'omitido por emergencias'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy Image') {
      steps{
         script {
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
  }
}