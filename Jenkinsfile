pipeline {
    agent { docker { image 'apache' } }
    stages {
        stage('Pull image') {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials')
        }
        stage('build') {
            steps {
                sh 'apache --version'
            }
        }
    }
}
