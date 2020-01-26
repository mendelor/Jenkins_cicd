pipeline {
    agent any
    options {
      timeout(time: 5, unit: 'MINUTES')
      disableConcurrentBuilds()
    }

    stages {
       stage ('built') {
          steps {
            script {
                docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    app = docker.build('mendelor/docker')

        } } } }
       parallel {
       stage ('run') {
         agent { label 'linux' }
          steps {
            script {
          app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   } }

          agent { label 'any'}
            steps {
              script {
            app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t")   } }

        }}}}
