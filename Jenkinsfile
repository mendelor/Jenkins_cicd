
pipeline {
  agent any
    stages {
        stage('Build') {
          agent {
            docker { 
              image 'php:7.2-cli' 
            }
        }
          steps { 
              sh 'docker build -t php5 . '
            }
        }

    }
}


