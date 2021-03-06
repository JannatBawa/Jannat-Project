pipeline {
  agent any
  stages {
    stage('Build with Maven') {
      steps {
        sh 'mvn clean install package'
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
}