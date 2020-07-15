pipeline {
   agent any
    stages {
      stage ("Cloning Git") {
        steps {
          git "https://github.com/mendelor/phtml.git"
        }
      }
      stage('Building image') {
        steps{
          script {
            sh 'docker build -t aaa  ":$BUILD_NUMBER" '
          }
        }
    }

}}

