node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
    stage('clean')  {
     
        sh "docker rm $(docker ps -a -q)"
        
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp12")
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


