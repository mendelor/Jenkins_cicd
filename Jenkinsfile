pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                sh 'docker-compose up '
            }
        }
        stage("run") {
            steps { 
                sh 'docker container start mysql:5.7'
            }
        }
    }
}
