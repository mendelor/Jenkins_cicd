pipeline {
    agent { docker { image 'nginx' } }
    stages {
        stage('build') {
            steps {
                sh 'nginx --version'
            }
        }
        stage('Push image') {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
              app.push("${env.BUILD_NUMBER}")
              app.push("latest")
            }
        }
    }
}
