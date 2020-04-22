pipeline {
  agent {
    docker {
      image "node:10-alpine"      
      args "--network=skynet"
    }
  }
  stages {
    stage("Build") {
      steps {
        sh "apk add --no-cache mongodb=3.4.4-r0 mongodb-tools"
        sh "chmod +x ./scripts/dropdb.sh"
        sh "npm install"
      }
    }
    stage("Test") {
      steps {
        sh "npm run test:ci"
      }
    }
  }
}
