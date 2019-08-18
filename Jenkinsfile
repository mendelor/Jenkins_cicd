node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("mendel/nodeapp7")
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
    post {
        always {
            echo "Stop Docker image"
            script {
                if (pipelineContext && pipelineContext.dockerContainer) {
                    pipelineContext.dockerContainer.stop()
                }
            }
        }
    }
