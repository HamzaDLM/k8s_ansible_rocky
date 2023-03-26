
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
                 echo 'P@ssword2020' | ansible-playbook rocky_init_with_ansible.yaml -i hosts -u root '''

            }
        }
        stage('test access to the server ') {
            steps {
                sh 'ssh ansible@${IP_ADDRESS}'
                sh 'ls'
                sh 'exit'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying.....'
            }
        }
    }
}
