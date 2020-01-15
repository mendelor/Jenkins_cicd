 pipeline {
     agent {
         docker { image 'java' }
     }
     stages {
         stage("Unit test") {
             sh "./gradlew compileJava"
             }
         }
     }

