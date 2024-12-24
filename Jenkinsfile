pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Gigajn/jetkins.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'npm install'
                    } else {
                        bat 'npm install'
                    }
                }
            }
        }
        stage('Run Unit Tests') {
            steps {
                script {
                    if (isUnix()) {
                        sh './run-tests.sh'
                    } else {
                        bat 'run-tests.bat'
                    }
                }
            }
        }
    }
}
