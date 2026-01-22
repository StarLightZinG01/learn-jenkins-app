pipeline {
    agent {
        docker {
            image 'node:18-alpine' // ใช้ Image นี้ที่มี Node.js มาให้แล้ว
            reuseNode true 
        }
    }
    stages {
        stage('Test npm') {
            agent {
                docker
            }
            steps {
                sh 'npm --version'
                sh 'node --version'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
    //  post {
    //     always {
    //         junit 'test-results/junit.xml'
    //     }
    // }
}
