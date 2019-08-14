pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh ' docker build -t jennn . '
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh ' docker run -d jennn '
            }
        }
    }
}
  
