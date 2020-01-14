pipeline {
    agent any
    options {
      timeout(time: 5, unit: 'MINUTES')
      disableConcurrentBuilds()
    }

    stages {
      stage ('test') {
       steps {
          sh 'chmod +x test.php'
          sh 'test.php'
      }
       }}}
