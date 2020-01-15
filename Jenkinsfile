pipeline {
    agent { docker 'python:3.5.1' }
    triggers { cron('* * * * *') }
    
        stages {
            stage('build') {
                steps {
                    sh 'python --version'
                }
            }
        }
    }

