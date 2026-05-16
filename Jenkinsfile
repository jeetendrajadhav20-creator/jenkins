pipeline {
    agent any

    environment {
        APP_NAME = "SampleApp"
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
                // Replace with your repo URL
                git branch: 'main', url: 'https://github.com/jeetendrajadhav20-creator/jenkins'
            }
        }

        stage('Build') {
            steps {
                echo "Building the application..."
                sh 'echo "Compiling code..."'
                sh 'mkdir -p build && echo "build successful" > build/output.txt'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'echo "All tests passed!"'
            }
        }

        stage('Package') {
            steps {
                echo "Packaging application..."
                sh 'tar -cvf sampleapp.tar build/'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                sh 'echo "Deployment successful to staging server"'
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }

        failure {
            echo "Pipeline failed. Check logs."
        }
    }
}
