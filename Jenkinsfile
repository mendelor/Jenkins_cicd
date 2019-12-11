pipeline {
    agent none

    stages {
        stage('Build') {
            agent { label 'linux' }
            steps {
                echo 'Starting the Pipeline'
                sh 'docker rm -f $(docker ps --all --quiet) || true'
                sh 'docker rmi -f $(docker images --quiet) || true'
            }
        }
    }

    post {
        success {
            echo 'This will run only if successful'
        }
    }
}
     
          
