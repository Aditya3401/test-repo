pipeline {
    agent any // any indicates any env

    triggers {
        // build is triggered when a push event is received from the GitHub webhook
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Aditya3401/test-repo.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Running the build'
            }
        }
        stage('Test') {
            steps {
                echo 'Running test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy the build'
            }
        }
    }

    post {
        success {
            echo 'Script has run successfully'
        }
        failure {
            echo 'Script has failed'
        }
    }
}
