node {
  stage 'Checkout'
    git url: 'https://github.com/mendelor/Jenkins_cicd'

  stage 'build'
     docker.build('aaaaa')

  stage 'deploy'
  sh './deploy.sh'
}
  
