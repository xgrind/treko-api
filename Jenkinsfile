pipeline {
  agent {
    docker {
      image "nodejs:10-ubuntu"      
      args "--network=skynet"
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
