node {
  stage 'build'
  docker.image('snjv0911/acmecorp-buildenv').inside {
    git 'https://github.com/snjv0911/docker-jenkins-demo-app.git'
    sh 'mvn install'
    archive 'target/*.war'
  }

  stage 'package'
  docker.build('snjv0911/acmecorp-app').push()

  stage 'deploy'
  sh './deploy.sh'
}
