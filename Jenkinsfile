pipeline {
    agent any

    // Manually define properties, including Office 365 Webhook
    options([
        pipelineTriggers([
            [$class: 'Office365ConnectorWebhookTrigger',
             webhooks: [[
                 name: 'Teams Webhook',
                 url: 'https://prod-120.westus.logic.azure.com:443/workflows/76a1bb770e6d43608398e71385ec37f4/triggers/manual/paths/invoke?api-version=2016-06-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=7lJZKsYcCfr6zFubyLhI9esXdNG-ExElTyg5SqpBSRo',
                 startNotification: true,
                 notifySuccess: true,
                 notifyFailure: true,
                 notifyAborted: true,
                 notifyNotBuilt: false,
                 notifyUnstable: true
             ]]
            ]
        ])
    ])

    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }
}
