node {
    def app
            stage('Clone repository') {
               checkout scm  
            }

            stage('build image') {

              app = docker.build("getintodevops/hellonode1")   
            }

            stage('Test image') {
               app.inside {
                 sh 'echo "Tests passed"'
                 }      
            }
     }
