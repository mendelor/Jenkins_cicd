pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        def image = docker.build('mendelor/hellonode123')
                        image.push()
                    }
                }
            }
        }
        stage('analyze') {
            steps {
                sh 'echo "docker.io/mendelor/hellonode123 `pwd`/Dockerfile" > anchore_images'
                anchore name: 'anchore_images'
            }
        }
        stage('teardown') {
            steps {
                sh'''
                    for i in `cat anchore_images | awk '{print $1}'`;do docker rmi $i; done
                '''
            }
        }
    }
}
