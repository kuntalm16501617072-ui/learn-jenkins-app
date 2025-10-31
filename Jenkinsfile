// pipeline {
//     agent any

//     stages {
//         stage('w/o docker') {
//             steps {
//                 sh 'echo "Hello World"'
//                 sh 'ls -la'
//                 sh 'touch container-no.txt'
//             }
//         }

//         stage('w/ docker') {
//             agent {
//                 docker {
//                     image 'node:18-alpine'
//                     reuseNode true
//                 }
//             }
//             steps {
//                 sh 'ls -la'
//                 sh 'echo "With Docker"'
//                 sh 'touch container-yes.txt'
//                 sh 'npm --version'
//             }
//         }
//     }
// }




// Npm setup in Jenkins
pipeline {
    agent any

    stages {
        stage('Build') {
            agent
            {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                } 
            }
        

            steps {
                    sh '''
                        ls -la
                        node --version
                        npm --version
                        npm ci
                        npm run build
                        ls -la
                    '''
                }
            }
    }
}
