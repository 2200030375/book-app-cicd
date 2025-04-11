pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git url: 'https://github.com/2200030375/book-app-cicd.git'
      }
    }
    stage('Install & Build') {
      steps {
        sh 'npm install'
        sh 'npm run build'
      }
    }
    stage('Deploy with Ansible') {
      steps {
        sh 'ansible-playbook -i ansible/inventory/hosts ansible/deploy.yml'
      }
    }
  }
}
