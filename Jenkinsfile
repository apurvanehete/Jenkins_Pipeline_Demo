pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: '872f84d6-0500-4d2d-ab78-ea58896914e0', url: 'https://github.com/apurvanehete/Demo_Python.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Hello in Build stage'
                sh 'python3 Exe_2_python.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Hello in Test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Hello in deploy'
            }
        }
    }
}

