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
                sh 'echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list'
            }
        }
    }
}