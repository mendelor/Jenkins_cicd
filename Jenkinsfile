pipeline {
    agent { docker { image 'apache' } }
    stages {
        stage('build') {
            steps {
                sh 'apache --version'
            }
        }
        stage('Pull image') {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials')
        }
    }
}
