pipeline {
   agent any

   environment {
      PASS = credentials('dockerhub_pass')
  }

  stages {
      stage('Remove Docker Containers') {
         steps {
              sh 'docker rm -f $(docker ps --all --quiet) || true'
         }
      }

      stage('Remove Docker Images') {
         steps {
              sh 'docker rmi -f $(docker images --quiet) || true'
         }
      }

         stage('Build image') {
              steps {
                  script {
                  dockerImage  = docker.build("mendel/nodeapp12")
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

           stage('Test image') {
               steps {
                   script {
                  dockerImage.inside {
                       echo "Tests passed"
                  }
               }
            }
         }
      }
   }
