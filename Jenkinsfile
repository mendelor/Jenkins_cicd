pipeline {
    agent { docker "httpd;2.4" }
    stages {
        stage("build") {
            steps {
                sh 'mvn clean install -Dmaven.test.failure.ignore=true'
            }
        }
    }
    post {
        always {
            archive "target/**/*"
            junit 'build.xml'
        }
    }
}
