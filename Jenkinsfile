pipeline {
    agent any
    options { 
      timeout(time: 5, unit: 'MINUTES') 
      disableConcurrentBuilds()  
    }
  

    stages { 
       stage ('pull image') {
          steps {
            script {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerhub_pass') {
                    def image = docker.build('mendelor/docker')
} } } } } } 
