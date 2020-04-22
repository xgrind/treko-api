pipeline {
  agent {
    docker {
      image "node:8-alpine:3.9.5"      
      args "--network=skynet"
    }
  }
  stages {
    stage("Build") {
      steps {
        sh "apk add --no-cache mongodb mongodb-tools"
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
