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

    stage('Create and Push Image to DockerHub') {
      steps {
        sh 'ansible-playbook Build_and_Push_image.yml'
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
}