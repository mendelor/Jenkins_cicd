pipeline {
    agent any

    environment {
        PASS = credentials('dockerhub_pass')
    }

    stages {
        stage('Configure') {
            steps {
                echo 'Create parameters file'
            }
        }
}
}
