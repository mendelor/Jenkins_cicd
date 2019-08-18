node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
    
    stage('Remove Docker Containers') {
        
      sh 'docker rm $(docker ps --all --quiet) || true'
    
    }

}


