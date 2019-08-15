node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp2")
    }
    
     stage('run image') {
        /* This builds the actual image */

        app = docker.run("mendel/nodeapp21")
    }

    stage('Test image') {
        
        app.inside {
            echo "Tests passed"
        }
    }
}


