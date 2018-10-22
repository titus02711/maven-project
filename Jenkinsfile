pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
        docker.withServer('tcp://host:1234') {
          sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
        }
      }
    }
  }
}
