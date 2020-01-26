pipeline  {
  agent { label 'linux' }
  stages {
    
    stage ('one') {

  steps {
      sh 'docker rm -f $(docker ps --all --quiet) || true'
      sh 'docker rmi -f $(docker images --quiet) || true'
  }
}
  } }


