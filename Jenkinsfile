pipeline {
    agent { docker 'php' }
    stages {
        stage("build") {
            steps {
                sh 'php --version'
            }
        }
    }
    post {
        success  {
            junit 'build.xml'
        }
    }
}
