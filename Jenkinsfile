pipeline {
    agent any
    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/Djerade/website.git'
            }
        }
        stage('Installer les dépendances') {
            steps {
                sh 'npm install'
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
// pipeline {
//     agent {
//         docker {
//             image 'node:20-alpine' 
//             args '-p 3000:3000' 
//         }
//     }
//     stages {
//         stage('Build') { 
//             steps {
//                 sh 'npm install' 
//             }
//         }
//     }
// }
// pipeline {
//      agent any
//      stages {
//         stage("Build") {
//             steps {
//                 sh "sudo npm install"
//                 sh "sudo npm run build"
//             }
//         }
//         stage("Deploy") {
//             steps {
//                 sh "sudo rm -rf /var/www/jenkins-react-app"
//                 sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
//             }
//         }
//     }
// }