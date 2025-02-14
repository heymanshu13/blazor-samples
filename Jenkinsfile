pipeline {
    agent any

    environment {
        BRANCH_NAME = env.BRANCH_NAME
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
                    branch 'main'   
                    branch 'testing' 
                }
            }
            steps {
                script {
                    if (BRANCH_NAME == 'main') {
                        echo "Running pipeline for main...."
                        
                    } else if (BRANCH_NAME == 'testing') {
                        echo "Running pipeline for testing....."
                        
                    } else {
                        echo "Skipping deployment for unrelated branches"
                    }
                }
            }
        }
    }
}
