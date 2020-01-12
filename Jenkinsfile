pipeline {
    agent any
    options { 
      timeout(time: 5, unit: 'MINUTES') 
      disableConcurrentBuilds()  
    }
  
    stages { 
       stage ('pull image') {
          steps {
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    app = docker.build('mendelor/docker')

        } } }
       stage ('run image') {
          app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   }

        }}
