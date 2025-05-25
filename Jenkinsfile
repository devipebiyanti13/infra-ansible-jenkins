pipeline {
  agent any
  environment {
    ANSIBLE_FORCE_COLOR = 'true'
  }
  stages {
    stage('Checkout Source') {
      steps {
        git url: 'https://github.com/devipebiyanti13/infra-ansible-jenkins.git'
      }
    }
    stage('Run Ansible Playbook') {
      steps {
        sshangent(['ansible-ssh-key']) {
            sh 'ansible-plyabook -i hosts.ini deploy.yml'
        }
      }
    }
  }
}
