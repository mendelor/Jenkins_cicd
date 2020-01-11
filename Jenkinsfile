pipeline {
    agent any

    options {
      disableConcurrentBuilds()
    }

  	stages {
  		stage("Build") {
  			steps { buildApp() }
  		}
    }
  }
  
// steps
  def buildApp() {
     def appImage  = docker.build("mendel/docker")
    }




