pipeline {
  agent any
   stages {
     stage('Initialize') {
       steps { 
         echo 'Starting the Pipeline'
         sh 'mvn clean'
         sh 'docker rm -f $(docker ps --all --quiet) || true'
         sh 'docker rmi -f $(docker images --quiet) || true'
      }
    }  
     stage('Build') {
       steps {
        script {
         dockerImage  = docker.build("mendel/nodeapp1")
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
   }
}
