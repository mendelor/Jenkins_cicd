pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'httpd:2.4'
                }
            }
            steps {
                sh ' docker build -t abdc . '
            }
        }
    }
}

