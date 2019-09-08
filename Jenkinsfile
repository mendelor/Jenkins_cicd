pipeline {
 agent any
   stages {
     stage('Initialize') {
       steps {
         echo 'Starting the Pipeline'
         sh 'docker rm -f $(docker ps --all --quiet) || true'
         sh 'docker rmi -f $(docker images --quiet) || true'
         sh 'ocker service rm $(docker service ls -q)'
      }
    }
     stage('Build image') {
       steps {
         sh 'docker service create --replicas 3 -p 80:80 --name serviceName1 nginx'
      }
    }
  }
}
