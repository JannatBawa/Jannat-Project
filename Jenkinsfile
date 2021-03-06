pipeline {
  agent any
  environment{
  PATH = "/opt/maven/bin:$PATH}
  stages {
    stage('Build with Maven') {
      steps {
        sh 'mvn clean install package'
      }
    }

  }
}
