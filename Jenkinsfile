pipeline {
    agent any

    stages {
        stage('Build') {
            agent { label 'linux' }
            steps {
                sh 'docker build -t blahbi . '
            }
        }
        stage('run') {
            agent { label 'linux' }
            steps {
                sh ' docker run -d -p 80:80 blahbi '
          }
       }
    }
}
