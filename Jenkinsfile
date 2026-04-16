pipeline{
agent any
environment {
DOCKERHUB_CREDENTAILS =""
IMAGE_NAME = ""
}
stages{
stage('Build Docker Image')
{
steps{
bat 'docker build -t %IMAGE_NAME%:latest."
}
}
stage('Login to DockerHub'){
steps {
withCredentials([usernamePassword(
credentailsId: "Docker-credentails',
usernameVariable: 'USER',
passwordVariable: 'PASS')])
                 {
                   bat 'echo %PASS% | docker login -u %USER% --password-stdin'
                 }
}
}
  stage ('Push Docker Image')
  steps{
    bat 'docker push %IMAGE_NAME%:latest'
  }
}
}
}
