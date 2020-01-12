pipeline {
    agent any
    options { 
      timeout(time: 5, unit: 'MINUTES') 
      disableConcurrentBuilds()  
    }
  
    stages { 
       stage ('built') {
          steps {
            script {
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    app = docker.build('mendelor/docker')

        } } } }
       stage ('run') {
          steps {
            script { 
          app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   

        }}}
        stage ('clean') {
           steps {
             script { 
               sh "docker ps -f name=${env.BUILD_NUMBER} -q | xargs --no-run-if-empty docker stop"
               sh "docker ps -a -f name=${env.BUILD_NUMBER} -q | xargs -r docker rm"   
        }}}}}
