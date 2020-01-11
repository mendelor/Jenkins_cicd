pipeline {
	agent any


	stages {

		stage("Build") {
			steps { buildApp() }
		}
 }


// steps
def buildApp() {
		sh 'docker build -t blahblii . '
  	}

