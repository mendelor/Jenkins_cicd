  pipeline {
      agent any

      stages {
          stage('Build') {
            agent {
              docker {
                image 'php:7.2-cli'
                
              }
            }
          }

      }
  }

