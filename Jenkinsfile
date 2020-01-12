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
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    def image = docker.build('mendelor/docker')
        } }
       stage ('run image') {
          def image.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   }

        }}}}
