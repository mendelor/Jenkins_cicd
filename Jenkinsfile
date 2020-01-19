pipeline {
    agent any 
    option { disableConcurrentBuilds() }
    
    stages { 
      stage ("test") {
        steps {
          sh 'hello'
        
         }      
      }
   }

    post {
         always {
              mail to: 'zqpmdj7@gmail.com'
       }
    }
 }
