pipeline {
  environment {
    registry = "bn8595/dockerwebapp"
    registryCredential = "bn8595"
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/bn8595/dockerwebapp.git'
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Test Image') {
      steps{
        scripts{
          dockerImage.inside{
            sh 'echo "Test Image"'
          }
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
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $registry:$BUILD_NUMBER"
       }
    }
    /*stage('Run Container') {
     /* steps {
      /*  sh "docker run -d --name bn8595/dockerwebapp"
     /* }
    /*}     
  }
}
