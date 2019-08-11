pipeline {
    agent { docker { image 'apache' } }
    stages {
        stage('build') {
            steps {
                sh 'apache --version'
            }
            sh "docker login -u=$REGISTRY_AUTH_USR -p=$REGISTRY_AUTH_PSW ${env.REGISTRY_ADDRESS}"
        }
    }
}
