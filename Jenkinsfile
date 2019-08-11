pipeline {
    agent { label 'docker' } // if you don't have other steps, 'any' agent works
    stages {
        stage('Back-end') {
            agent {
                docker {
                  label 'docker'  // both label and image
                  image 'maven:3-alpine'
                }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
              docker {
                label 'docker'  // both label and image
                image 'node:7-alpine' 
              }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
