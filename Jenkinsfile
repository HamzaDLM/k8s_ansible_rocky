pipeline {
    agent {
        node {
        label 'Ubuntu-agent'
             }
    }
    
    stages {
        stage('Initialize & Install Dependencies') {
            steps { 
                sh 'ansible-playbook initialize.yaml -i hosts -u root'
            }
        }
        stage('Setup Controller Nodes') {
            steps {
                sh 'ansible-playbook controllers.yaml -i hosts -u root'
            }
        }
        stage('Setup Worker Nodes') {
            steps {
                sh 'ansible-playbook workers.yaml -i hosts -u root'
            }
        }
    }
}
