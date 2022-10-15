pipeline {
    agent {label 'master'}

    stages {
        stage('Clone') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/tush6016/eks-cluster-deployment.git']]])
            }
        }
        stage('Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Action') {
            steps {
                sh 'terraform plan'
            }
        }
    }
}
