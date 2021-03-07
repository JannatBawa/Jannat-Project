pipeline {
  agent any
  stages {
    stage('Build Code') {
      steps {
        sh '''mvn clean install package
'''
        sh 'ansible-playbook Copy_War_to_Docker_directory.yml'
      }
    }

    stage('Processing Docker Image') {
      steps {
        sh 'ansible-playbook Build_and_Push_image.yml'
      }
    }

    stage('Deploying on Kubernetes cluster') {
      steps {
        sh '''ansible-playbook Kubernetes-Deployment.yml
ansible-playbook Kubernetes-Service.yml'''
      }
    }

  }
  environment {
    PATH = "/opt/maven/bin:$PATH"
  }
  triggers {
    githubPush()
  }
}