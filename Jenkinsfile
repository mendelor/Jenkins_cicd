

pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        dockerImage = docker.build('mendelor/httpd')
                    
                    }
                }
            }
        }  
        stage('Run image') {
          steps {
           script {
           dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")}
        } } } }
