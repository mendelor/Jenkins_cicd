pipeline {
    agent any 
    options { disableConcurrentBuilds() }
    
    stages { 
      stage ("test") {
        steps {
          sh './test_calculator.py'
        
         }      
      }
   }
 }
