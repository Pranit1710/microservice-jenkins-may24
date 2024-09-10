pipeline {
    agent any

    tools{
        nodejs "node"
    }

    stages {
        stage('Git Checkout') {
            steps {
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '530aad2c-250b-4f94-b53f-42bc4b74c93c', url: 'https://github.com/Pranit1710/microservice-jenkins-may24.git']])
            }
        }
        
        stage('Install dependencies') {
            steps {
               sh 'sudo apt install npm'
               sh 'npm test'
            }
        }
        
        stage('Build') {
            steps {
                sh 'node index.js'
            }
        }

        stage('Build image') {
            steps {
                sh 'docker build -t node-cart .'
            }
        }
    }
}
