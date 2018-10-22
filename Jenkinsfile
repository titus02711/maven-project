pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
        docker.withServer('tcp://172.26.30.205:2375') {
          sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
        }
      }
    }
  }
}
