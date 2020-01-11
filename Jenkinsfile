  pipeline {
  	agent any
  
  
  	stages {
  
  		stage("Build") {
  			steps { buildApp() }
  		}
    }}
  
  
  // steps
    buildApp() {
       sh 'docker rmi -f $(docker images --quiet) || true'
    }

