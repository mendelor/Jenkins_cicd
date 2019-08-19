pipeline {
    agent any

    environment {
        PASS = credentials('dockerhub_pass')
    }

    stages {
        stage('Configure') {
            steps {
                sh 'docker rm -f $(docker ps --all --quiet) || true'
            }
        }
}
}

