pipeline {
    agent { docker { image 'httpd:2.4' } }
    stages {
        stage('build') {
            steps {
                sh 'httpd --version'
            }
        }
        stage('run') {
            steps {
                sh 'docker run -dit --name my-running-app -p 80:80 httpd:2.4'
            }
        }
    
    }
}
