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
            office365ConnectorSend webhookUrl: 'https://prod-120.westus.logic.azure.com:443/workflows/76a1bb770e6d43608398e71385ec37f4/triggers/manual/paths/invoke?api-version=2016-06-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=7lJZKsYcCfr6zFubyLhI9esXdNG-ExElTyg5SqpBSRo',
                status: 'SUCCESS',
                message: "Build #${env.BUILD_NUMBER} for branch ${env.BRANCH_NAME} succeeded.",
                factDefinitions: [
                    [name: "Branch", value: "${env.BRANCH_NAME}"],
                    [name: "PR URL", value: "${env.CHANGE_URL}"],
                    [name: "PR Author", value: "${env.CHANGE_AUTHOR}"],
                    [name: "PR Title", value: "${env.CHANGE_TITLE}"]
                ]
        }
        failure {
            office365ConnectorSend webhookUrl: 'https://prod-120.westus.logic.azure.com:443/workflows/76a1bb770e6d43608398e71385ec37f4/triggers/manual/paths/invoke?api-version=2016-06-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=7lJZKsYcCfr6zFubyLhI9esXdNG-ExElTyg5SqpBSRo',
                status: 'FAILED',
                message: "Build #${env.BUILD_NUMBER} for branch ${env.BRANCH_NAME} failed.",
                factDefinitions: [
                    [name: "Branch", value: "${env.BRANCH_NAME}"],
                    [name: "PR URL", value: "${env.CHANGE_URL}"],
                    [name: "PR Author", value: "${env.CHANGE_AUTHOR}"],
                    [name: "PR Title", value: "${env.CHANGE_TITLE}"]
                ]
        }
    }
}
