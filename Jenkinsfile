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
            }
        }
    }
}