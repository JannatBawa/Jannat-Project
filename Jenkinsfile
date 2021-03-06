pipeline {
  agent any
  stages {
    stage('Build with Maven') {
      steps {
        sh '''mvn clean install package
'''
        sh 'ansible-playbook Copy_War_to_Docker_directory.yml'
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
}
