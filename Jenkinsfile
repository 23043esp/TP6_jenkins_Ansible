pipeline {
    agent any

    environment {
        ANSIBLE_INVENTORY = 'inventaire.ini'
        ANSIBLE_PLAYBOOK = 'deploy.yml'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/23043esp/TP6_jenkins_Ansible.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: "${ANSIBLE_PLAYBOOK}",
                    inventory: "${ANSIBLE_INVENTORY}"
                )
            }
        }
    }
}
