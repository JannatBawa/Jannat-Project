pipeline {
  agent any
  stages {
    stage('Build with Maven') {
      steps {
        sh '''mvn clean install package
ansible-playbook Copy_War_to_Kubernetes_host.yml'''
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
}