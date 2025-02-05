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
                sh 'echo "This is Jenkins Pipeline"'
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y gnupg software-properties-common'
                sh 'wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null'
                sh 'gpg --no-default-keyring --keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg --fingerprint'
                sh 'echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list'
                sh 'sudo apt update'
                sh 'sudo apt-get install terraform -y'
            }
        }
        stage('Terraform Initialize') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Terraform apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
        stage('Terraform Destroy Approval') {
            steps {
                input message: 'Approve or Destroy', ok: 'Destroy'
            }
        }
        stage('Terraform Destroy') {
            steps {
                sh 'terraform destroy --auto-approve'
            }
        }
    }
}
