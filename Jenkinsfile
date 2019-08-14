pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                docker build -t aaa .
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
  
