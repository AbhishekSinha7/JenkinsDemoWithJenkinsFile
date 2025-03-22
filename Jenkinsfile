pipeline {
    agent any
    stages {
        stage('Validate Branch') {
            when {
                expression { env.BRANCH_NAME == 'release' }
            }
            steps {
                echo "Confirmed running on release branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Build') {
            when {
                expression { env.BRANCH_NAME == 'release' }
            }
            steps {
                echo "Pull request merged into release. Proceeding with build..."
                // Insert build steps here.
            }
        }
    }
}
