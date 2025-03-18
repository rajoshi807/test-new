pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo "Branch: ${env.BRANCH_NAME}"
                    echo "PR URL: ${env.CHANGE_URL}"
                    echo "PR Author: ${env.CHANGE_AUTHOR}"
                    echo "PR Title: ${env.CHANGE_TITLE}"
                }
            }
        }
    }
}
