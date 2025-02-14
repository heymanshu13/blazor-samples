pipeline {
    agent any

    environment {
        BRANCH_NAME = "testing"
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo "Checking out code for branch: ${BRANCH_NAME}"
                    checkout scm
                }
            }
        }

        stage('Build & Deploy') {
            when {
                anyOf {
                    branch 'main'   // Run only when on the 'admin-portal' branch
                    branch 'testing'  // Add other project-specific branches as needed
                }
            }
            steps {
                script {
                    if (BRANCH_NAME == 'main') {
                        echo "Running pipeline for main...."
                        // Run admin portal deployment steps here
                    } else if (BRANCH_NAME == 'testing') {
                        echo "Running pipeline for testing....."
                        // Run other project deployment steps here
                    } else {
                        echo "Skipping deployment for unrelated branches"
                    }
                }
            }
        }
    }
}
