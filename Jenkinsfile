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
                sh 'sudo apt install gnupg'
                sh 'wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null'
                sh 'gpg --no-default-keyring --keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg --fingerprint'
                
        }
    }
}
}