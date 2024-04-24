pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/juanosorio0219/jenkins-lab'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }
    }
}
