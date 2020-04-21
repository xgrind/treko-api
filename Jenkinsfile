pipeline {
  agent {
    docker {
      image "node:12-ubuntu"      
    }
  }
  stages {
    stage("Build") {
      steps {
        sh "apt install mongodb"
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
