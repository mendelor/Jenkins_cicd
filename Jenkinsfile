pipeline {
    agent any

    stages {
        stage('Build') {
            agent { label 'linux' }
            steps {
                sh 'docker build -t blahb . '
            }
        }
        stage('run') {
            agent { label 'linux' }
            steps {
                sh ' docker run -d -p 80:80 blahb '
          }
       }
    }
}
