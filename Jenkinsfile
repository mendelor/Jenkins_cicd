  pipeline {
  	agent any
  
  
  	stages {
  
  		stage("Build") {
  			steps { buildApp() }
  		}
   }
  
  
  // steps
    buildApp() {
       dockerImage  = docker.build("mendel/nodeapp1")
    }

