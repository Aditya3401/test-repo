pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Aditya3401/test-repo.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
    }
}
