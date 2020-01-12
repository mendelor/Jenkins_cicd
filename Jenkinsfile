pipeline {
    agent any
    options { 
      timeout(time: 5, unit: 'MINUTES') 
      disableConcurrentBuilds()  
    }
  
    stages { 
       stage ('built') {
          steps {
            script {
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    app = docker.build('mendelor/docker')

        } } } }
       stage ('run') {
          steps {
            script { 
          app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   

        }}}

        stage('Approval') {
            input {
               message 'Should we continue?'
             }
          steps {
             echo 'Deploying'

             }
          }

        stage ('clean') {
           steps {
             script { 
               sh "docker ps -f name=${env.BUILD_NUMBER} -q | xargs --no-run-if-empty docker stop"
               sh "docker ps -a -f name=${env.BUILD_NUMBER} -q | xargs -r docker rm"   
        }}}

        stage('analyze') {
            steps {
                sh 'echo "docker.io/mendelor/docker `pwd`/Dockerfile" > anchore_images'
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
        }}
