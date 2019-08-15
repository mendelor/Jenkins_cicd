pipeline {
    agent {
         docker {
                 image 'httpd:2.4'
                }
          }
               
    stages {
         stage('Build') {
            steps {
                sh 'docker build -t httpdddd1 . '
                  }
                        }
        stage('run') {
            steps {
                sh ' docker run -d -p 80:80 httpdddd1 '
          }
       }
    }
}
