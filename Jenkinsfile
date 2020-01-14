pipeline {
    agent { docker 'httpd:2.4' }
    stages {
        stage("build") {
            steps {
                sh 'python --version'
            }
        }
    }
    post {
        success  {
            junit 'build.xml'
        }
    }
}
