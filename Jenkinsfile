// Declarative //
pipeline {
  agent vm_integrador_byssh

  stages {
    stage('Test') {
      steps {
        sh '''
          docker --version // Check the version of docker
        '''
      }
    }
    stage('Buils') {
      steps {
        sh '''
          sh "docker build ---tag = nodesimple4testinjenkins:${env.BUILD_NUMBER} "
        '''
      }
    }
    stage('Docker TAG') {
      steps {
        sh '''
          docker --version // Check the version of docker
        '''
      }
    }
    stage('Docker push') {
      steps {
        sh '''
          docker --version // Check the version of docker
        '''
      }
    }
  }
}