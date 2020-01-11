  pipeline {
  	agent any
  
  
  	stages {
  
  		stage("Build") {
  			steps { buildApp() }
  		}
   }
  
  
  // steps
    buildApp() {
      script {
  		sh 'docker build -t blahblii . '
    	}}

