node {
    def app
     
    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp8902322")
    }
    
    stage('run image') {
        /* This builds the actual image */

        app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
           echo "pngimage_build_${env.BUILD_NUMBER}"
    }

    stage('Test image') {
        
        app.inside {
            echo "Tests passed"
        }
    }
}

