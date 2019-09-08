pipeline {
 agent any
   stages {
     stage('Initialize') {
       steps {
         echo 'Starting the Pipeline'
         sh 'docker rmi -f $(docker images --quiet) || true'
         sh 'docker service rm $(docker service ls -q)'
      }
    }
     stage('Build image') {
       steps {
         sh 'docker service create --replicas 3 -p 80:80 --name serviceName1 nginx'
      }
    }
  }
}
