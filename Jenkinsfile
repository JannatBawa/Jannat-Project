pipeline {
  agent any
  stages {
    stage('Build with Maven') {
      steps {
        sh '''mvn clean install package
mv /var/lib/jenkins/workspace/Jannat-Project_master/webapp/target/webapp.war /opt/Docker'''
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
}