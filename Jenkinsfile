 pipeline {
     agent {
         docker { image 'java' }
     }
     stages {
         stage("Compile") {
             steps {
                 sh "./gradlew compileJava"
             }
         }
     }
 }

