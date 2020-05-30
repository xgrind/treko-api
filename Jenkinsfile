pipeline {
  agent {
    docker {
      image "node:12-ubuntu"            
    }
  }
  stages {
    stage("Build") {
      steps {       
        sh "npm install"
      }
    }    
  }
}
