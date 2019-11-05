   pipeline {
        agent any
          options {
           timeout(time: 3, unit: 'MINUTES')
          }
          stages {
            stage('Cleanup') {
              steps {
                echo 'Starting the Pipeline'
                sh 'docker rm -f $(docker ps --all --quiet) || true'
                sh 'docker rmi -f $(docker images --quiet) || true'
             }
           }  

         }}
