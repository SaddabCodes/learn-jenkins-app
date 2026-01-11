pipeline {
  agent any

  stages {
    stage('Build') {
      agent {
        docker {
          image 'node:20-alpine'
          reuseNode true
        }
      }
      steps {
        // cleanWs()
        sh '''
          echo "Node version:"
          node --version

          echo "NPM version:"
          npm --version

          echo "Installing dependencies..."
          npm ci

          echo "Building app..."
          CI=true npm run build

          echo "Build completed"
          ls -la
        '''
      }
    }
  }
}
