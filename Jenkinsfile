pipeline {
    agent {
         docker {
                 image 'nginx:latest'
                }
          }
               
    stages {
         stage('Build') {
            steps {
                sh 'docker build -t nginxtest . '
                  }
                        }
        stage('run') {
            steps {
                sh ' docker run -d -p 80:80 nginxtest '
          }
       }
    }
}
