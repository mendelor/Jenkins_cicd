pipeline {
    agent { docker { image 'php:5.2' } }
    stages {
        stage('build') {
            steps {
                sh 'php --version'
            }
        }
        stage('run') {
            steps {
                sh 'docker run -d php'
            }
        }
    
    }
}
