pipeline {
    agent { docker { image 'httpd' } }
    stages {
        stage('build') {
            steps {
                sh 'httpd --version'
            }
        }
    }
}
