pipeline{
  agent any

  stages{
    stage('build'){
      agent{
        docker{
          image 'node:lts-alpine3.23'
          reUseNode true
        }
      }
      steps{
        sh '''
        ls -la
        node --version
        npm --version
        npm ci
        npm run build
        ls -la
        '''
      }
    }
  }
}