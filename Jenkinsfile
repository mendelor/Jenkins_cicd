pipeline {
  agent any
    stages {
        stage('Build') {
          agent {
            docker {
              image 'php:7.2-cli'
              label 'mydocker'
            }
        }
          steps {
              sh 'docker build -t apchi12345 . '
            }
        }

    }
}
     

     
          
