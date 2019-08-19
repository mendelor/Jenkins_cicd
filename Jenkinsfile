  pipeline {
      agent any

      stages {
          stage('Build') {
              steps {
                  sh 'docker rm -f $(docker ps --all --quiet) || true'
              }
          }
          stage('run') {
              steps {
                  sh 'docker rmi -f $(docker images --quiet) || true'
            }
         }
      }
  }

