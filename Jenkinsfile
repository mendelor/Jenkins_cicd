pipeline {
    agent none

    stages {
        stage('Clean') {
            agent { label 'linux' }
            steps {
                echo 'Starting the Pipeline'
                sh 'docker rm -f $(docker ps --all --quiet) || true'
                sh 'docker rmi -f $(docker images --quiet) || true'
            }
        }

        stage('Build') {
            agent { label 'linux' }
            steps {
            script {
            dockerImage  = docker.build("mendel/docker")
            }
         }
      }
   }
}

    post {
        success {
            echo 'This will run only if successful'
        }
    }
}
