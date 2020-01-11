pipeline {
    agent any

    options {
      disableConcurrentBuilds()
    }
    stages {
  		stage("Test - Unit tests") {
  			steps { runUnittests() }
		}}

  	stage {
  		stage("Build") {
  			steps { buildApp() }
  		}
      
  		stage("Deploy - Dev") {
  			steps { deploy('dev') }
      }
    }
  }
  
// steps
def buildApp() {
	dir ('section_4/code/cd_pipeline' ) {
		def appImage = docker.build("hands-on-jenkins/myapp:${BUILD_NUMBER}")
    	}
    }

    def runUnittests() {
    	sh "pip3 install --no-cache-dir -r ./Jenkins_cicd/requirements.txt"
    	sh "python3 Jenkins_cicd/test_flask_app.py"
    }

    
def deploy(environment) {

	def containerName = ''
	def port = ''

	if ("${environment}" == 'dev') {
		containerName = "app_dev"
		port = "80"
	} 
	else {
		println "Environment not valid"
		System.exit(0)
	}

	sh "docker ps -f name=${containerName} -q | xargs --no-run-if-empty docker stop"
	sh "docker ps -a -f name=${containerName} -q | xargs -r docker rm"
}

