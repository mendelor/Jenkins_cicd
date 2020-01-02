pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        def image = docker.build('mendelor/docker')
                        image.pull()
                    }
                }
            }
        }  
        stage('analyze') {
            steps {
                sh 'docker run mendelor/docker'
                
            }
        } } }
