pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
              echo 'Building..'
              script {
                build job: 'test_job', parameters: [
                [$class: 'LabelParameterValue', name: 'node', label: "${env.NODE_NAME}" ]
                ]
}}}}}

     
          
