 pipeline {
 agent any
   stages {
     stage('Initialize') {
       steps { 
         echo 'Starting the Pipeline'
         sh 'docker rm -f $(docker ps --all --quiet) || true'
         sh 'docker rmi -f $(docker images --quiet) || true'
      }
    }  
     stage('Build image') {
       steps {
        script {
         dockerImage  = docker.build("mendelor/nodeapp6698")
        }
     }
  }
     stage('Run image') {
       steps {
        script {
        dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
    
         }
       }
     }  

     stage('Push image') {
      docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
          app.push("${env.BUILD_NUMBER}")
          }
              echo "Trying to Push Docker Build to DockerHub"
  }
