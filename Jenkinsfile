pipeline {
    agent none

    stages {
        stage('Clean') {
            agent { label 'linux' }
            steps {
               
                sh 'docker rm -f $(docker ps --all --quiet) || true'
                sh 'docker rmi -f $(docker images --quiet) || true'
                sh 'service apache2 stop'
            }
        }

        stage('Build') {
            agent { label 'linux' }
            steps {
            script {
            dockerImage  = docker.build("mendel/nodeapp12345")
            }
        }
    }
        stage('Run image') {
            agent { label 'linux' }
            steps {
            script {
            dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")


            }
         }
      }
   }
}

