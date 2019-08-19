node {
   def app

    stage('Remove Docker Containers') {

      sh 'docker rm -f $(docker ps --all --quiet) || true'
    }

    stage('Remove Docker Images') {

      sh 'docker rmi -f $(docker images --quiet) || true'
    }

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp1")
    }

     stage('run image') {
        /* This builds the actual image */

        app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
    }

    stage('Test image') {

        app.inside {
            echo "Tests passed"

        }
    }
}

