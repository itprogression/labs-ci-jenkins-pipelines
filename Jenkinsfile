// Declarative //
pipeline {
  agent any
  environment{
    DOCKER_HUB = credentials ('docker_hub_lastranikos')
  }





  stages {
    stage('Test') {
      steps {
        sh '''
          docker --version // Check the version of docker
          ls -lah
        '''
      }
    }
    stage('Buils') {
      steps {
        sh "docker build --tag=nodesimplefortestinjenkins:$env.BUILD_NUMBER} ."
        sh """
          docker build --tag=nodesimplefortestinjenkins:$env.BUILD_NUMBER} .
          docker ps
          docker image ls
        """
      }
    }
    stage('Docker login to docker hub') {
      steps {
        sh '''
          echo $DOCKER_HUB_PSW | docker login -u $DOCKER_HUB_USR --password-stdin
        '''
      }
    }
    stage('Docker push') {
      steps {
        sh '''
          docker push NameRepoDockerHub/dockerIMG:tag
        '''
      }
    }
  }
}