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

  		stage("Deploy - Dev") {
  			steps { deploy('dev') }
      }
    }

  
// steps
def deploy(environment) {

sh "docker ps -f name=${containerName} -q | xargs --no-run-if-empty docker stop"
sh "docker ps -a -f name=${containerName} -q | xargs -r docker rm"
}

def buildApp() {
	dir ('section_4/code/cd_pipeline' ) {
		def appImage = docker.build("hands-on-jenkins/myapp:${BUILD_NUMBER}")
    	}
    }



