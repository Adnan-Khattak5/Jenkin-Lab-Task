pipeline {
    agent any // This tells Jenkins to use any available agent to run the pipeline

    environment {
        CI = 'true' // Sets the CI environment variable to true, used by some tools to indicate running in a CI environment
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Adnan-Khattak5/Jenkin-Lab-Task.git'
                checkout scm
            }
        }
        
        stage('Install dependencies') {
            steps {
                script {
                    // Using Node.js 'node' and 'npm' to install dependencies
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Builds the React app for production to the 'build' folder
                    sh 'npm run build'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Runs tests
                    // The CI=true environment variable treats test warnings as errors. Remove if not needed.
                    sh 'npm test'
                }
            }
        }

        // Add more stages for deployment or further testing if needed
    }
    
    post {
        always {
            // Cleanup, archiving artifacts, or sending notifications could be done here
        }
    }
}
