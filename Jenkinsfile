pipeline {
    agent any 
    stages {
        stage('Terraform Jenkins Pipeline test') { 
            steps {
                sh 'echo "This is Jenkins Pipeline"'
            }
        }
        stage('Terraform Download and Install') { 
            steps {
                sh 'sudo apt update'
                sh 'wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg'
                sh 'sudo apt update && sudo apt install terraform -y'
        }
    }
}
}