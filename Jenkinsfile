pipeline {
    agent { docker 'python:3.5.1' }
    triggers { cron('1 * * * *') }
    
        stages {
            stage('build') {
                steps {
                    sh 'python --version'
                }
            }
        }
    }

