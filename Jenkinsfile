pipeline {
    // Run this pipeline on any available Jenkins build agent
    agent any 

    // Define custom variables to reuse across your stages
    environment {
        APP_NAME = "My-Learning-App"
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Jenkins automatically pulls your code, but this prints a confirmation
                echo "Successfully fetched code for ${env.APP_NAME} from GitHub"
            }
        }

        stage('Run Test Script') {
            steps {
                echo "Starting automated testing..."
                // Make the script executable and run it
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }

        stage('Simulate Deployment') {
            steps {
                // You can add your Docker, Kubernetes, or Ansible steps here later
                echo "Deploying ${env.APP_NAME} to the target environment..."
            }
        }
    }

    // Post-actions run automatically based on whether the stages passed or failed
    post {
        success {
            echo "Pipeline complete! Everything passed smoothly."
        }
        failure {
            echo "Pipeline failed. Please check the console logs for errors."
        }
    }
}
