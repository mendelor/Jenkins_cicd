pipeline 
  agent { label 'linux' }
  stages {
    
    stage ('one') {

  steps {
      echo 'Starting the Pipeline'
      sh 'docker rm -f $(docker ps --all --quiet) || true'
      sh 'docker rmi -f $(docker images --quiet) || true'
  }
}
}
