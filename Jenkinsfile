node {
    def app

            stage('Clone repository') {
               checkout scm  
            }

            stage('build image') {

                  dockerImage = docker.build("getintodevops/hellonode1")

                 
             }
           }

