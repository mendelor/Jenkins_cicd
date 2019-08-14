pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build docker image"
                script {
                    docker built -t aaa .
                }
            }
        }
        stage('Run') {
            steps {
                echo "Run docker image"
                script {
                    docker run -d -p 80:80 aaa
                }
            }
        }
    }
}
  
