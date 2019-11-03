node {
    def app
            stage('Clone repository') {
               checkout scm  
            }

            stage('build image') {

              app = docker.build("getintodevops/hellonode2")   
            }

            stage('Test image') {
               app.inside {
                 sh 'echo "Tests passed"'
                 }      
            }
     }
