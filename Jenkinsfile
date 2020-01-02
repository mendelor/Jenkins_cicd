pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                      time dockerImage = docker.build('mendelor/httpd')
                      
                    }
                }
            }
        }  
        stage('Publish test results') {
        steps {
        sh "./gradlew test"
        }
        }

        stage('Run image') {
          steps {
           script {
              dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")}
        } } } }
