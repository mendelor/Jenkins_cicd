
    pipeline {

    agent any

    stages {
      stage(‘Build’) {
        steps {
          sh '/var/lib/jenkins/workspace/test-pipe/docker-compose.yml up --build'
        }
      }
    }
}


