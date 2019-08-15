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
                  sh "docker login -u=mendelor -p=1d6ac2f01q11"
                
              }
          }

      }
  }

