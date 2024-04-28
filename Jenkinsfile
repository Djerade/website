pipeline {
    agent any
    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/Djerade/website.git'
            }
        }
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('Installer les dépendances') {
            steps {
                sh 'sudo apt install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}