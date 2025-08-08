pipeline {
    agent any
    triggers {
        // Poll GitHub every 1 minute for changes
        pollSCM('* * * * *')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'dev', url: 'https://github.com/Aditya3401/test-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example build command
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example test command
                // sh 'npm test'   <-- your actual test command here
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to $DEPLOY_PATH ..."
                sh """
                    mkdir -p $DEPLOY_PATH
                    cp -r * $DEPLOY_PATH/
                    echo 'Deployed at: ' \$(date)
                """
            }
        }
    }

    post {
        success {
            echo '✅ Build and Deployment successful.'
        }
        failure {
            echo '❌ Build or Deployment failed.'
        }
    }
}
