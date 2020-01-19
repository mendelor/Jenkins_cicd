pipeline {
    agent any 
    options { disableConcurrentBuilds() }
    
    stages { 
      stage ("test") {
        steps {
          sh 'echo hello'
        
         }      
      }
   }

    post {
         always {
              mail to: 'zqpmdj14@gmail.com',
                   subject: "Completed Pipeline",
                   body: "Your build completed"
       }
    }
 }

