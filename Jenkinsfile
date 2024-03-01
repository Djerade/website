pipeline {
    // agent {
    //     docker {
    //         image 'node:20.11.1-alpine3.19' 
    //         args '-p 4000:4000' 
    //     }
    // }
    agent any
    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/Djerade/website.git'
            }
        }
        // stage("Restore npm packages") {
        //     steps {
        //         // Writes lock-file to cache based on the GIT_COMMIT hash
        //         writeFile file: "next-lock.cache", text: "$GIT_COMMIT"

        //         cache(caches: [
        //             arbitraryFileCache(
        //                 path: "node_modules",
        //                 includes: "**/*",
        //                 cacheValidityDecidingFile: "package-lock.json"
        //             )
        //         ]) {
        //             sh "npm install"
        //         }
        //     }
        // }
        stage("Build") {
            steps {
                // Writes lock-file to cache based on the GIT_COMMIT hash
                writeFile file: "next-lock.cache", text: "$GIT_COMMIT"

                cache(caches: [
                    arbitraryFileCache(
                        path: ".next/cache",
                        includes: "**/*",
                        cacheValidityDecidingFile: "next-lock.cache"
                    )
                ]) {
                    // aka `next build`
                    sh "npm run build"
                }
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
