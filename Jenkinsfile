pipeline {
    agent { docker { image 'nginx' } }
    stages {
        stage('build') {
            steps {
                sh 'nginx --version'
            }
        }
        stage('Pull image') {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials')
        }
    }
}
