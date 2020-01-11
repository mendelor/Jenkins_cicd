pipeline {
	agent any


	stages {

		stage("Build") {
			steps { buildApp() }
		}
 }


// steps
def buildApp() {
	dir ('section_4/code/cd_pipeline' ) {
		def appImage = docker.build("hands-on-jenkins/myapp:${BUILD_NUMBER}")
  	}
  }
