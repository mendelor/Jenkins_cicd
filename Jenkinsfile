  pipeline {
  	agent any
  
  
  	stages {
  
  		stage("Build") {
  			steps { buildApp() }
  		}
   }
  
  
  // steps
  def buildApp() {
      script {
  		sh 'docker build -t blahblii . '
    	}}

