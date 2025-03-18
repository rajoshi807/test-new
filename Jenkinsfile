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
    post {
        success {
            office365ConnectorSend webhookUrl: 'https://outlook.office.com/webhook/your-webhook-url',
                status: 'SUCCESS',
                message: "Build #${env.BUILD_NUMBER} for branch ${env.BRANCH_NAME} succeeded.",
                facts: [
                    [name: "Branch", value: "${env.BRANCH_NAME}"],
                    [name: "PR URL", value: "${env.CHANGE_URL}"],
                    [name: "PR Author", value: "${env.CHANGE_AUTHOR}"],
                    [name: "PR Title", value: "${env.CHANGE_TITLE}"]
                ]
        }
        failure {
            office365ConnectorSend webhookUrl: 'https://outlook.office.com/webhook/your-webhook-url',
                status: 'FAILED',
                message: "Build #${env.BUILD_NUMBER} for branch ${env.BRANCH_NAME} failed.",
                facts: [
                    [name: "Branch", value: "${env.BRANCH_NAME}"],
                    [name: "PR URL", value: "${env.CHANGE_URL}"],
                    [name: "PR Author", value: "${env.CHANGE_AUTHOR}"],
                    [name: "PR Title", value: "${env.CHANGE_TITLE}"]
                ]
        }
    }
}
