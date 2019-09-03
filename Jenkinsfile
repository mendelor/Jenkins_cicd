  pipeline {
     agent any
       options {
        timeout(time: 3, unit: 'MINUTES')
       }
       stages {
         stage('Cleanup') {
           steps {
             echo 'Starting the Pipeline'
             sh """
               docker ps -a \
                 | awk '{ print \$1,\$2 }' \
                 | grep imagename \
                 | awk '{print \$1 }' \
                 | xargs -I {} docker rm -f {}
               """
          }
        }

    }
 }
