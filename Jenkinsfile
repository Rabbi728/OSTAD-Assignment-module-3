pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }
        stage('Clone') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/Rabbi728/OSTAD-Assignment-module-3.git'
                }
            }
        }
        stage('Install') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'npm run check'
                }
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            junit '**/test-*.xml'
        }
        success {
            echo 'Build successful'
        }
        failure {
            echo 'Build failed'
        }
    }
}
