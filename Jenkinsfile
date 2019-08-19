pipeline {
    agent any

    environment {
        PASS = credentials('dockerhub_pass')
    }

    stages {
        stage('Remove Docker Containers') {
            steps {
                sh 'docker rm -f $(docker ps --all --quiet) || true'
            }
        }

        stages {
            stage('Build image') {
                steps {
                    app = docker.build("mendel/nodeapp1")
                }
            }
}
}

