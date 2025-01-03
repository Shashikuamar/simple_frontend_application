pipeline {
    agent any

    environment {
        DEPLOY_ENV = 'development'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code of the current branch
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the frontend application...'
                // Normally, you might run a build tool here (e.g., Webpack, Gulp, or any other)
                // For simplicity, we will skip build steps as it's a static frontend app
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Here you can run tests for your frontend app (e.g., unit tests with Jest or Mocha)
                // In this case, it’s a simple app, so we’re skipping it
            }
        }

        stage('Deploy') {
            when {
                branch 'develop'  // Only deploy to development if on the develop branch
            }
            steps {
                echo 'Deploying to the development environment...'
                // Replace this with actual deployment command, for example:
                // Deploy to a development server, S3, or any web hosting service
                sh 'echo "Deploying the app to development environment"'
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully."
        }
        failure {
            echo "Pipeline failed. Check the logs for errors."
        }
    }
}

