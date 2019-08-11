pipeline {
    environment {
      registry = "docker_hub_account/mendelor"
      registryCredential = 'docker-hub-credentials'
    }
    
    agent any
    
    stages {
        stage('build') {
            steps {
                sh 'apache --version'
            }
        }
    }
}
