pipeline {
    agent any
    options {
      timeout(time: 5, unit: 'MINUTES')
      disableConcurrentBuilds()
    }

    stages{
      stage ('test') {
          dir ('unitest')
      }
       }}
