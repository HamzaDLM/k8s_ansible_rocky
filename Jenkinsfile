
pipeline {
    agent {
        node {
        label 'Ubuntu-agent'
             }
    }
    
    stages {
        stage('Build') {
            steps {
                
                print "DEBUG: parameter IP_ADDRESS = ${IP_ADDRESS}"
                sh 'echo $IP_ADDRESS >> hosts'  
                sh ' cat hosts'
                sh 'echo ${IP_ADDRESS} '
                sh ''' #!/bin/bash
                 echo "hello world"                  
                 echo 'P@ssword2020' | ansible-playbook ubuntu_init_with_ansible.yaml -i hosts -u root '''

            }
        }
        stage('mise en place website ') {
            steps {
                sh 'ansible-playbook install-nginx-andwebsite.yaml -i hosts '
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying.....'
            }
        }
    }
}
