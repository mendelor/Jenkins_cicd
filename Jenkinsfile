  pipeline {
  	agent any
  
  
  	stages {
  
  		stage("Build") {
  			steps { buildApp() }
  		}
    }}
  
  
  // steps
    def buildApp() {
       def appImage  = docker.build("mendel/nodeapp1")
    }




