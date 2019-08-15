pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    docker.build ('httpd:2.4')
                }
            }
            steps {
                sh ' docker build -t abdc . '
            }
        }
    }
}

