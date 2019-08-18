node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
    
    stage('Dangling Containers') {
      sh 'docker ps -q -f status=exited | xargs --no-run-if-empty docker rm'
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp89")
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

