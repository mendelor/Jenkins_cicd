 pipeline {
     agent {
         docker { image 'java' }
     }
     stages {
         stage("Unit test") {
             steps {
                 sh "./gradlew test"
             }
         }
     }
 }
