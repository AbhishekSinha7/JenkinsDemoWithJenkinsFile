pipeline {
    agent any
    stages {
        stage('Check Branch') {
            steps {
                script {
                    // Early exit: if not on release branch, skip the rest of the pipeline
                    if (env.BRANCH_NAME != 'release') {
                        echo "Not on release branch (${env.BRANCH_NAME}), skipping build steps."
                        // Optionally, you can set the build result to SUCCESS or NOT_BUILT.
                        currentBuild.result = 'NOT_BUILT'
                        return
                    }
                }
            }
        }
        stage('Build') {
            // Alternatively, you can also use the when block to guard individual stages:
            when {
                expression { env.BRANCH_NAME == 'release' }
            }
            steps {
                echo "Pull request merged into release. Proceeding with build..."
                // Add your build, test, and deployment steps here.
            }
        }
    }
}
