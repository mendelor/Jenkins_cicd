pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('run') {
            steps {
                sh 'docker run -d maven'
            }
        }
    
    }
}
