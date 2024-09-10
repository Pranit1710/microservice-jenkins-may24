pipeline {
    agent any

    tools{
        maven "mvn"
    }

    stages {
        stage('Git Checkout') {
            steps {
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '530aad2c-250b-4f94-b53f-42bc4b74c93c', url: 'https://github.com/Pranit1710/microservice-jenkins-may24.git']])
            }
        }
        
        stage('Install dependencies') {
            steps {
               sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'node index.js'
            }
        }
    }
}
