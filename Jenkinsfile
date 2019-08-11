pipeline {
    agent { docker { image 'apache' } }
    stages {
        stage('build') {
            steps {
                sh 'apache --version'
            }
        }
    }
}
