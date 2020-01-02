pipeline {
agent any
stages {

    stage "build"
        // build without tests
        checkout scm
        sh './gradlew clean build -x test -x integTest'

    stage "unit test"
        // returnStatus: true here will ensure the build stays yellow
        // when test cases are failing
        sh (script: './gradlew test', returnStatus: true)
        step([$class: 'JUnitResultArchiver',
             testResults: '**/build/test-results/test/TEST-*.xml'])

    if (currentBuild.result == null) {
        // if unit tests have failed currentBuild will be 'UNSTABLE'
        // and we should not bother to run integration tests
        stage "integration test"
            sh (script: './gradlew integTest', returnStatus: true)
            step([$class: 'JUnitResultArchiver',
                 testResults: '**/build/test-results/integTest/TEST-*.xml'])
    }
} }
